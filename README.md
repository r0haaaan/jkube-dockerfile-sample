# JIB Sample with Docker Maven Plugin

1. Make sure you're logged into your docker hub account.
2. Modify ImageConfiguration in pom.xml and add your docker hub username there:
```
            <image>
              <!-- Add your user name here -->
              <name>rohankanojia/helloworld-java:${project.version}</name>
              <alias>hello-world</alias>
              <build>
                <from>openjdk:latest</from>
                <assembly>
                  <descriptorRef>artifact</descriptorRef>
                </assembly>
                <cmd>java -jar maven/${project.name}-${project.version}.jar</cmd>
              </build>
              <run>
                <wait>
                  <log>Hello World!</log>
                </wait>
              </run>
            </image>
```
3. Run `mvn docker:build` to build your image, it would be automatically pushed to docker hub.
![alt text](https://i.imgur.com/Erx8w5d.png)
