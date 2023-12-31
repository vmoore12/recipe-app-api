FROM python:3.9-alphine3.13 
LABEL maintainer="vickie.moore26@gmail.com"

ENV PYTHONUNBUFFERED 1

# This copies the requirments file into docker image
COPY ./requirements.txt /tmp/requirements.txt
COPY ./app /app
# This sets the working directory
WORKDIR /app
EXPOSE 8000

RUN python -m venv /py && \
    /py/bin/pip install --upgrade pip && \
    /py/bin/pip install -r /tmp/requirements.txt && \
    rm -rf /tmp && \
    adduser \
        --disaple-password \
        --no--create--home \
        django-user

ENV PATH='/py/bin:$PATH'

USER django-user

