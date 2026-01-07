FROM python:latest

RUN apt update
RUN apt install -y curl wget unzip tar git qrencode python3-venv dnsutils
RUN git clone https://github.com/xMiokay/rustdesk-api-server /opt/rustdesk-api-server
RUN mkdir -p /var/log/rustdesk-server-api/

COPY install.docker.sh /scripts/install.sh
RUN chmod +x /scripts/install.sh
RUN /scripts/install.sh

COPY api_config.py /opt/rustdesk-api-server/api/api_config.py

COPY run.docker.sh /scripts/run.sh
RUN chmod +x /scripts/run.sh
EXPOSE 9400

ENTRYPOINT [ "/scripts/run.sh" ]
