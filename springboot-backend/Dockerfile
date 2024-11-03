FROM openjdk:17 as build

WORKDIR /app

COPY . .

RUN chmod +x mvnw && ./mvnw package -DskipTests

FROM openjdk:17

WORKDIR /app

COPY --from=build /app/target/*.jar app.jar

CMD ["java", "-jar", "app.jar"]