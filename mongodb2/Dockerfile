FROM centos:6.6

MAINTAINER shuchao <shuc324@gmail.com>
add ./*.repo /etc/yum.repo.d/
RUN { \
    echo "[mongodb]"; \
    echo "name=MongoDB Repository"; \
    echo "baseurl=http://downloads-distro.mongodb.org/repo/redhat/os/x86_64/"; \
    echo "gpgcheck=0"; \
    echo "enabled=1"; \
} > /etc/yum.repos.d/mongodb-org-2.6.repo

RUN yum install -y mongodb-org
RUN mkdir -p /data/db/mongodb /data/logs/mongodb && chmod 777 -R /data/db /data/logs

ADD run.sh /run.sh
ADD set_mongodb_password.sh /set_mongodb_password.sh

EXPOSE 27017

CMD ["/run.sh"]
