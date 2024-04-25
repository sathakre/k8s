FROM centos:7

RUN yum install epel-release -y && yum install java-11-openjdk -y

WORKDIR /opt/

ADD https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.100/bin/apache-tomcat-8.5.100.tar.gz .

RUN tar -xzvf apache-tomcat-8.5.100.tar.gz

WORKDIR /opt/apache-tomcat-8.5.100

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war /opt/apache-tomcat-8.5.100/webapps/student.war

ADD https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar /opt/apache-tomcat-8.5.100/lib/mysql-connector.jar

EXPOSE 8080

WORKDIR /opt/apache-tomcat-8.5.100/bin

CMD ./catalina.sh run