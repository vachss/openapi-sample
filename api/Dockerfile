FROM python:3-alpine

RUN mkdir -p /usr/src
WORKDIR /usr/src

COPY requirements.txt /usr/src

RUN apk add --update build-base
RUN python3 -m pip install --upgrade pip
RUN python3 -m pip install -r requirements.txt --no-cache-dir

COPY src /usr/src
COPY ./openapi/openapi.yaml /openapi.yaml
EXPOSE 8080

ENTRYPOINT ["python3"]

CMD ["app.py"]
