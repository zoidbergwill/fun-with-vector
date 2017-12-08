FROM debian:jessie
RUN set -ex; \
  apt-get update; \
  apt-get install -y apt-transport-https curl wget; \
  curl 'https://bintray.com/user/downloadSubjectPublicKey?username=pcp' | apt-key add -; \
  echo "deb https://dl.bintray.com/pcp/jessie jessie main" | tee -a /etc/apt/sources.list; \
  apt-get update; \
  apt-get install -y pcp pcp-webapi; \
  rm -rf /var/apt/lists/*

CMD ["service pmcd start && exec /usr/lib/pcp/bin/pmwebd"]
