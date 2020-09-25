FROM fishingfly/maven-aliyun:v3.6 AS builder
WORKDIR /app
COPY . .
RUN mvn clean install

FROM openjdk:8-jre-alpine
COPY --from=builder /app/target/demo-0.0.1-SNAPSHOT.jar /app.jar
CMD ["java", "-jar", "/app.jar"]
