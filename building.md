# How to use source to build? 

2022-04-16/lorne   

## Prerequisites

When you compile locally, the following errors may occur that the jar files cannot be obtained. Please download the jar files and install them in the local repository.

* commands 3.3.0 (https://mvnrepository.com/artifact/org.eclipse/core-commands/3.3.0)
```
 <dependency>
    <groupId>org.eclipse</groupId>
    <artifactId>core-commands</artifactId>
    <version>3.3.0</version>
 </dependency>
```
this pom name is org.eclipse.core-commands, but the jar file name is org.eclipse.core-commands.3.3.0.jar, so you need to rename the jar file.


* beanshell 2.1.1 (https://github.com/beanshell/beanshell/releases/tag/2.1.1)
```
 <dependency>
    <groupId>org.beanshell</groupId>
    <artifactId>bsh</artifactId>
    <version>2.1.1</version>
 </dependency>
```

this repository is not found, so you need to download the jar file from the following URL and install it in the local repository.

* syslog4j 0.9.46 (https://mvnrepository.com/artifact/org.syslog4j/syslog4j/0.9.46)
```
 <dependency>
    <groupId>org.syslog4j</groupId>
    <artifactId>syslog4j</artifactId>
    <version>0.9.46</version>
 </dependency>
```
you can download the jar file from the following URL and install it in the local repository.


## Building it

This is a Maven project, and to build it use the following command:

```
$ mvn clean install -DskipTests=true
```

The build result will be a Pentaho package located in `target`.

## Packaging / Distributing it

Packages can be built by using the following command:

```
$ mvn clean package -DskipTests=true
```

add `-DskipTests=true` to skip the tests (even though you shouldn't as you know)


## Assemblies

The packaged results will be in the `target/` sub-folders of `assemblies/*`.

For example, a distribution of the Desktop Client (CE) can then be found in: `assemblies/client/target/pdi-ce-*-SNAPSHOT.zip`.

