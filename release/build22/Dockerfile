FROM ubuntu:22.04
MAINTAINER Andy Wick <andy.wick@oath.com>

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
apt-get install -y lsb-release ruby-dev make python3-pip git libtest-differences-perl sudo wget apt-utils tzdata && \
(cd /tmp && wget https://packages.ntop.org/apt-stable/22.04/all/apt-ntop-stable.deb && dpkg -i apt-ntop-stable.deb) && \
apt-get update && \
apt-get install -y pfring && \
gem install --no-document fpm && \
pip3 install awscli && \
git clone https://github.com/arkime/arkime && \
(cd arkime; git checkout main; ./easybutton-build.sh --nothirdparty) && \
rm -rf arkime && \
rm -rf /var/lib/apt/lists/*
