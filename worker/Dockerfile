FROM maven:3-openjdk-11-slim

WORKDIR /app 

COPY . .

RUN mvn compile && \
    mvn clean test && \
    mvn package -DskipTests && \
    mv target/worker-jar-with-dependencies.jar /run/worker.jar && \
    rm -rf /app

CMD ["java","-jar","/run/worker.jar"]