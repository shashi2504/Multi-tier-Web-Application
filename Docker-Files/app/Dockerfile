FROM maven:3.9.9-eclipse-temurin-21-jammy AS buildImage
RUN git clone https://github.com/shashi2504/Multi-tier-Web-Application.git
RUN cd Multi-tier-Web-Application && mvn install

FROM tomcat:10-jdk21
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=buildImage Multi-tier-Web-Application/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]