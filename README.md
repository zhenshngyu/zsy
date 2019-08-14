# zsy
spring:
  profiles:
    active:
      - dev
---
server:
  port: 7001
  
spring:
  profiles: dev
  application:
    name: greecloud-config-eureka-client

eureka:
  instance:
    hostname: localhost   #localhost     #eureka服务端的实例名称
  client:
    register-with-eureka: false   #false表示不向注册中心注册自己。
    fetch-registry: false   #false表示自己端就是注册中心，我的职责就是维护服务实例，并不需要去检索服务
    service-url:
      defaultZone: http://localhost:7001/eureka/   #设置与Eureka Server交互的地址查询服务和注册服务都需要依赖这个地址。
---
server:
  port: 7002
  
spring:
  profiles: test
  application:
    name: greecloud-config-eureka-client

eureka:
  instance:
    hostname: localhost   #localhost     #eureka服务端的实例名称
  client:
    register-with-eureka: false   #false表示不向注册中心注册自己。
    fetch-registry: false   #false表示自己端就是注册中心，我的职责就是维护服务实例，并不需要去检索服务
    service-url:
      defaultZone: http://localhost:7002/eureka/   #设置与Eureka Server交互的地址查询服务和注册服务都需要依赖这个地址。
---
