FROM centos:7.7.1908
MAINTAINER liyi888

RUN rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -ivh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm --force

ADD CentOS-Base.repo /etc/yum.repos.d
ADD epel.repo /etc/yum.reops.d

RUN yum install -y httpd httpd-devel
RUN yum install -y php70w php70w-mysql php70w-mbstring php70w-mcrypt php70w-gd php70w-imap
RUN yum install -y php70w-ldap php70w-odbc php70w-pear php70w-xml php70w-xmlrpc php70w-pdo
RUN sed -ri 's/#ServerName www.example.com:80/ServerName www.cloud.com/g' /etc/httpd/conf/httpd.conf

ADD index.html /var/www/html

ADD run.sh /run.sh
RUN chmod 775 /run.sh

EXPOSE 80
CMD ["/run.sh"]
