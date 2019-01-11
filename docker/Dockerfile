FROM ubuntu:18.04
ARG branch=master

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get -y install openssl ca-certificates curl wget git cmake python3 g++ && rm -rf /var/lib/apt/lists/* \
    && cd / && git clone --depth 1 -b $branch https://github.com/boscore/bos.cdt.git --recursive \
    && cd /bos.cdt/ \
    && ./build.sh \
    && ./install.sh \
    && cd .. \
    && rm -rf ./bos.cdt

USER root


#  https://hub.docker.com/r/gxk666/bos.cdt/tags
#  docker pull gxk666/bos.cdt
#  docker run  -v /root:/root/  -it bos.cdt:latest    /bin/bash