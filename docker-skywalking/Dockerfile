FROM centos:7

# Timezone, Asia/Shanghai by default
ENV Timezone=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$Timezone /etc/localtime && echo '$Timezone' > /etc/timezone

RUN yum install -y wget && \
    yum install -y java-1.8.0-openjdk

WORKDIR /app

ADD http://mirror.bit.edu.cn/apache/skywalking/6.1.0/apache-skywalking-apm-6.1.0.tar.gz .

RUN tar -xf apache-skywalking-apm-6.1.0.tar.gz && \ 
    mv apache-skywalking-apm-bin skywalking && \ 
    echo "tail -f /dev/null" >> /app/skywalking/bin/startup.sh

CMD ["/bin/sh","-c","/app/skywalking/bin/startup.sh" ]