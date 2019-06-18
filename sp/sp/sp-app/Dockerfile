FROM python:3.6.6-alpine3.7

RUN apk add --update \
    build-base libffi-dev openssl-dev \
    xmlsec xmlsec-dev \
  && rm -rf /var/cache/apk/*

ADD requirements.txt /tmp
RUN pip instll -r /tmp/requirements.txt
RUN apt-get install -y libxml2-dev libxmlsec1-dev libxmlsec1-openssl && \
    apt-get install xmlsec1

EXPOSE 8000
CMD python manage.py migrate && python manage.py runserver 0.0.0.0:8000