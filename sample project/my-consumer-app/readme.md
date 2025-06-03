Step1: create a sample project

mkdir my-maven-project
cd my-maven-project
mvn archetype:generate -DgroupId=com.example -DartifactId=my-consumer-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false


structure:
my-maven-project/
 ├── pom.xml
 ├── src/
 ├── target/



Step2: in pom.xml add the below 2 things:

1. specify the repo from where the jar will be downloaded
  <repositories>
    <repository>
      <id>codeartifact</id>
      <url>https://demo-domain-390402546375.d.codeartifact.ap-south-1.amazonaws.com/maven/demo-repo/</url>
    </repository>
  </repositories>

2. specify the jar to be download

    <dependency>
      <groupId>com.amex</groupId>
      <artifactId>amex</artifactId>
      <version>1.0.0</version>
      <scope>compile</scope>
    </dependency>
3. make sure settings.xml is properfly configured

Step3: mvn clean install -s settings.xml


output:

$ mvn clean install -s ../../settings.xml 
[INFO] Scanning for projects...
[INFO] 
[INFO] --------------------< com.example:my-consumer-app >---------------------
[INFO] Building my-consumer-app 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
Downloading from codeartifact: https://demo-domain-390402546375.d.codeartifact.ap-south-1.amazonaws.com/maven/demo-repo/com/amex/amex/1.0.0/amex-1.0.0.pom
Downloaded from codeartifact: https://demo-domain-390402546375.d.codeartifact.ap-south-1.amazonaws.com/maven/demo-repo/com/amex/amex/1.0.0/amex-1.0.0.pom (386 B at 464 B/s)
Downloading from codeartifact: https://demo-domain-390402546375.d.codeartifact.ap-south-1.amazonaws.com/maven/demo-repo/com/amex/amex/1.0.0/amex-1.0.0.jar
Downloaded from codeartifact: https://demo-domain-390402546375.d.codeartifact.ap-south-1.amazonaws.com/maven/demo-repo/com/amex/amex/1.0.0/amex-1.0.0.jar (92 kB at 169 kB/s)
[INFO]
[INFO] --- clean:3.2.0:clean (default-clean) @ my-consumer-app ---
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ my-consumer-app ---
[WARNING] Using platform encoding (Cp1252 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory C:\Users\RAHUL\Desktop\Work\aws codeartifact\test2\sample project\my-consumer-app\src\main\resources
[INFO]
[INFO] --- compiler:3.11.0:compile (default-compile) @ my-consumer-app ---
[INFO] Changes detected - recompiling the module! :source
[WARNING] File encoding has not been set, using platform encoding Cp1252, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 1.8] to target\classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- resources:3.3.1:testResources (default-testResources) @ my-consumer-app ---
[WARNING] Using platform encoding (Cp1252 actually) to copy filtered resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory C:\Users\RAHUL\Desktop\Work\aws codeartifact\test2\sample project\my-consumer-app\src\test\resources
[INFO]
[INFO] --- compiler:3.11.0:testCompile (default-testCompile) @ my-consumer-app ---
[INFO] Changes detected - recompiling the module! :dependency
[WARNING] File encoding has not been set, using platform encoding Cp1252, i.e. build is platform dependent!
[INFO] Compiling 1 source file with javac [debug target 1.8] to target\test-classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO]
[INFO] --- surefire:3.1.2:test (default-test) @ my-consumer-app ---
[INFO] Using auto detected provider org.apache.maven.surefire.junit.JUnit3Provider
Downloading from central: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/3.1.2/surefire-junit3-3.1.2.pom
Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/3.1.2/surefire-junit3-3.1.2.pom (3.1 kB at 13 kB/s)
Downloading from central: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/3.1.2/surefire-junit3-3.1.2.jar
Downloaded from central: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/3.1.2/surefire-junit3-3.1.2.jar (24 kB at 297 kB/s)
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.example.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.017 s -- in com.example.AppTest
[INFO] 
[INFO] Results:
[INFO]
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO]
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ my-consumer-app ---
[INFO] Building jar: C:\Users\RAHUL\Desktop\Work\aws codeartifact\test2\sample project\my-consumer-app\target\my-consumer-app-1.0-SNAPSHOT.jar
[INFO] 
[INFO] --- install:3.1.1:install (default-install) @ my-consumer-app ---
[INFO] Installing C:\Users\RAHUL\Desktop\Work\aws codeartifact\test2\sample project\my-consumer-app\pom.xml to C:\Users\RAHUL\.m2\repository\com\example\my-consumer-app\1.0-SNAPSHOT\my-consumer-app-1.0-SNAPSHOT.pom
[INFO] Installing C:\Users\RAHUL\Desktop\Work\aws codeartifact\test2\sample project\my-consumer-app\target\my-consumer-app-1.0-SNAPSHOT.jar to C:\Users\RAHUL\.m2\repository\com\example\my-consumer-app\1.0-SNAPSHOT\my-consumer-app-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  4.635 s
[INFO] Finished at: 2025-06-03T01:19:19+05:30
[INFO] ------------------------------------------------------------------------
