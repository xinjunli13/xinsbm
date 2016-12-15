# xinsbm开始学习Spring boot + Mybatis框架
第一次运行
2016-12-15 11:51:56.484  INFO 4403 --- [           main] com.xin.sbm.XinsbmApplication            : Starting XinsbmApplication on Xinjls-MacBook-Pro.local with PID 4403 (/Users/xinjl/ProStu/xinsbm/target/classes started by xinjl in /Users/xinjl/ProStu/xinsbm)
2016-12-15 11:51:56.488  INFO 4403 --- [           main] com.xin.sbm.XinsbmApplication            : No active profile set, falling back to default profiles: default
2016-12-15 11:51:56.586  INFO 4403 --- [           main] s.c.a.AnnotationConfigApplicationContext : Refreshing org.springframework.context.annotation.AnnotationConfigApplicationContext@50dfbc58: startup date [Thu Dec 15 11:51:56 CST 2016]; root of context hierarchy
2016-12-15 11:51:59.741  INFO 4403 --- [           main] o.s.j.e.a.AnnotationMBeanExporter        : Registering beans for JMX exposure on startup
2016-12-15 11:51:59.765  INFO 4403 --- [           main] com.xin.sbm.XinsbmApplication            : Started XinsbmApplication in 14.343 seconds (JVM running for 15.691)
2016-12-15 11:51:59.786  INFO 4403 --- [       Thread-1] s.c.a.AnnotationConfigApplicationContext Disconnected from the target VM, address: '127.0.0.1:53050', transport: 'socket'
: Closing org.springframework.context.annotation.AnnotationConfigApplicationContext@50dfbc58: startup date [Thu Dec 15 11:51:56 CST 2016]; root of context hierarchy
2016-12-15 11:51:59.788  INFO 4403 --- [       Thread-1] o.s.j.e.a.AnnotationMBeanExporter        : Unregistering JMX-exposed beans on shutdown

Process finished with exit code 0

在官网(http://start.spring.io/)上generate project，将生成的项目导入idea中，运行之后控制台输出“Unregistering JMX-exposed beans on shutdown”，tomcat也没有运行。寻找原因，看了下pom.xml文件中tomcat依赖关系如下：

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-tomcat</artifactId>
        <scope>provided</scope>
    </dependency>
    
 将<scope>provided</scope>注释掉，重新运行项目便可启动嵌入的tomcat服务器：Tomcat started on port(s): 8080 (http)
