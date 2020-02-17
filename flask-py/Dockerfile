FROM ubuntu:16.04

MAINTAINER Muhammad Fakhri Abdillah "fakhri@cilsyfiolution.com"

RUN apt-get update -y && \
    apt-get install -y python-pip python-dev python-flask

# We copy just the requirements.txt first to leverage Docker cache
COPY ./requirements.txt /app/requirements.txt

WORKDIR /app

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

COPY . /app

ENTRYPOINT [ "python" ]

CMD [ "app.py" ]