# Use the httpd-parent image as base
LABEL io.openshift.expose-services="8080:http"
LABEL io.k8s.description="A basic Apache HTTP Server child image, uses ONBUILD" \
      io.k8s.display-name="Apache HTTP Server" \
      io.openshift.expose-services"808:http" \
      io.openshift.tags="apache, httpd"
FROM quay.io/redhattraining/httpd-parent
EXPOSE 8080
RUN sed -i "s/Lisen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd
USER 1001

