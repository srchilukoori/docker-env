ARG jre_base_version=17-al2023
FROM amazoncorretto:${jre_base_version}

RUN mkdir /opt/workspace
RUN mkdir /opt/staging

RUN yum update -y
RUN yum -y install wget tar gzip

ARG MVN_VER=3.9.2
RUN cd /opt/staging\
; wget https://dlcdn.apache.org/maven/maven-3/${MVN_VER}/binaries/apache-maven-${MVN_VER}-bin.tar.gz\
; tar -xzvf apache-maven-${MVN_VER}-bin.tar.gz \
; rm apache-maven-${MVN_VER}-bin.tar.gz \
; mv apache-maven-${MVN_VER} /opt/workspace/

ENV M2_HOME /opt/workspace/apache-maven-${MVN_VER}
ENV PATH $M2_HOME/bin:$PATH

RUN cd /opt; rm -rf staging

CMD ["bash"]