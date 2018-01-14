# Service Discovery

Discover services with
	- Spring Cloud Consul
	- Spring Cloud Zookeeper
	- Spring Cloud Netflix
	
Spring Cloud Netflix
	- Spring Cloud Netflix Eureka Server
	- Spring Cloud Netflix Eureka Client
	
Discovery Server:
	Actively managed registry of service locations
	Source of truth
	One or more instances
	
<!-- https://mvnrepository.com/artifact/org.springframework.cloud/spring-cloud-starter-eureka-server -->

To create Discovery Server -
	Add the following in the pom.xml
<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-dependencies</artifactId>
			<version>Camden.SR2</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>

<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-eureka-server</artifactId>
    <version>1.4.1.RELEASE</version>
</dependency>

In application.properties:
spring.application.name=discovery-server

In main class add -
@EnableEurekaServer

#Using Spring cloud eureka client in a service
```
<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-dependencies</artifactId>
			<version>Camden.SR2</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>

Add a new dependency in dependencies

<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-eureka-server</artifactId>
    <version>1.4.1.RELEASE</version>
</dependency>
```

#Using spring cloud eureka client in a Service
***application.properties***
```
spring.application.name=service
eureka.client.service-url.defaultZone=http:localhost:8761/eureka
```

***Main Class***
`@EnableDiscoveryClient`