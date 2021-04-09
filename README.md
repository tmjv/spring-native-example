# spring-native-example
An example application built with Spring Native.

## Prerequisites 

* Java 11
* Apache Maven 3.8.1
* GraalVM 21 if building the application to native executable application by GraalVM native image

## Build

Like general Spring Boot applications, run the following command  to run the application in JVM.

```bash
$ mvn spring-boot:run
```

Or run the `DemoApplication` in your IDEs.

### Build Docker Image

```bash
$ mvn spring-boot:built-image -Pspring-native,build-docker-image
```

Run the application in docker container.

```bash
$ docker run -rm  hantsy/spring-native-demo:latest
```

### Build Native Image

> It requires installation of GraalVM.

```bash
$ mvn clean package -Pspring-native,build-native-image
```

Run the application.

```bash
$ ./target/com.example.demo.demoapplication
```



## Functional Tests

When the application is running at *localhost:8080*,  you can perform a `FunctionalTests` to verify the APIs as a HTTP Client view.

```bash
$ mvn clean test -Pfunctional-test
```

