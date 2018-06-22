FROM ubuntu:16.04

ENV libs 'automake libcurl4-gnutls-dev make gcc curl bzip2 locales libev-dev bison libbison-dev'
RUN apt-get update \
  && apt-get install -y ${libs}

ENV roswell_archive_url 'https://github.com/roswell/roswell/archive/release.tar.gz'
RUN echo 'install roswell' \
  && curl -SL ${roswell_archive_url} \
  | tar -xzC /tmp/ \
  && cd /tmp/roswell-release \
  && sh bootstrap \
  && ./configure \
  && make \
  && make install \
  && rm -rf /tmp/roswell-release
