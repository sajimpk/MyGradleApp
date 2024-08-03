# Step 1: Initialize the Project
Create a new directory for your project:
```java
mkdir MyGradleApp
cd MyGradleApp
```
## Initialize the Gradle project:
```
gradle init
```
## Select the following options when prompted:

Type of project to generate: application
Implementation language: Java
Build script DSL: Groovy
Test framework: JUnit 4
Project name: MyGradleApp
Source package: com.mycompany.mygradleapp (or any package name you prefer)

# Step 2: Configure the build.gradle File
### dependencies site 
I can coppy any *dependencies* on this site `https://mvnrepository.com/`

After initializing the project, your build.gradle file should look something like this:
```java
plugins {
    id 'java'
    id 'application'
}

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.slf4j:slf4j-api:1.7.30'
    testImplementation 'junit:junit:4.13.1'
}

application {
    mainClassName = 'App'
}
```
# Step 3: Create the Main Application File
Navigate to the src/main/java/com/mycompany/mygradleapp directory and create a file named App.java:

```
mkdir -p src/main/java/com/mycompany/mygradleapp
nano src/main/java/com/mycompany/mygradleapp/App.java
```
Add the following code to App.java:
```java
public class App {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }

    public String getGreeting() {
        return "Hello, World!";
    }
}
```
# Step 4: Create a Test File
Navigate to the src/test/java/com/mycompany/mygradleapp directory and create a file named AppTest.java:

```java
mkdir -p src/test/java/com/mycompany/mygradleapp
nano src/test/java/com/mycompany/mygradleapp/AppTest.java
```
## Add the following code to AppTest.java:

```java
import org.junit.Test;
import static org.junit.Assert.*;

public class AppTest {
    @Test
    public void testAppHasAGreeting() {
        App classUnderTest = new App();
        assertNotNull("app should have a greeting", classUnderTest.getGreeting());
    }
}
```
# Step 5: Build and Run the Application
Run the application:

```
./gradlew run
```
You should see Hello, World! printed in the console.

Run the tests:
```
./gradlew test
```
This will compile and run your unit tests.
