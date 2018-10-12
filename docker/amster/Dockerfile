# Amster Container that configures AM.
#
#
# Copyright (c) 2016-2017 ForgeRock AS. Use of this source code is subject to the
# Common Development and Distribution License (CDDL) that can be found in the LICENSE file
FROM openjdk:8-alpine 

COPY amster.zip .
RUN mkdir -p /opt/amster && unzip -q amster.zip -d /opt/amster 

#COPY *.zip /opt/forgerock
RUN apk add bash
COPY *.sh /opt/amster/
# put these in the path as well - for convenience.
COPY *.sh /usr/local/bin/

WORKDIR /opt/amster

USER 11111

ENTRYPOINT ["/opt/amster/docker-entrypoint.sh"]

CMD ["configure"]
