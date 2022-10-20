# Starburst Error Prone Bug Checkers

Collection of [Error Prone](https://github.com/google/error-prone) bug checkers for the
[Trino](https://trino.io/) ecosystem, e.g. connectors, functions, authenticators, and other
extensions.

## Bug Checkers

* `TrinoExperimentalSpi` - Check for usages of Trino `@Experimental` SPIs.

## Usage

To use the checkers configure your project to build with the Error Prone Java compiler and add
`error-prone-checks` annotation processor.

To customize that pass an additional compiler argument, e.g. `-Xep:TrinoExperimentalSpi:ERROR`.
Allowed values are: `ERROR`, `WARNING`, `SUGGESTION`, `OFF`.

### Maven

In `pom.xml`:

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
    <configuration>
        ...
        <annotationProcessorPaths>
            ...
            <path>
                <groupId>io.starburst.errorprone</groupId>
                <artifactId>error-prone-checks</artifactId>
                <version>1.0</version>
            </path>
        </annotationProcessorPaths>
    </configuration>
</plugin>
```
