FROM ubuntu:bionic

LABEL maintainer="R3GISTRY"
LABEL description="Minecraft-Bedrock-Server in Docker."

WORKDIR /tmp/

ADD \
https://minecraft.azureedge.net/bin-linux/bedrock-server-1.12.0.28.zip \
.

RUN \
apt-get update \
&& apt-get -y --no-install-recommends install libcurl4 libssl1.1 unzip \
&& rm -rf /var/lib/apt/lists/* \
&& unzip bedrock-server-1.12.0.28.zip \
&& mkdir /usr/local/minecraft-bedrock-server/ \
&& mv bedrock_server /usr/local/minecraft-bedrock-server/minecraft-bedrock-server \
&& chmod +x /usr/local/minecraft-bedrock-server/minecraft-bedrock-server \
&& mv libCrypto.so /usr/local/minecraft-bedrock-server/ \
&& rm -r * \
&& apt-get -y --auto-remove purge unzip

VOLUME ["/mnt/minecraft-bedrock-server/"]

ENTRYPOINT ["/usr/local/minecraft-bedrock-server/minecraft-bedrock-server"]
