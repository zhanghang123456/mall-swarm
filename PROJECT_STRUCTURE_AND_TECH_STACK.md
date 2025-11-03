# Mall-Swarm 项目完整目录树和技术栈

## 项目概述

`mall-swarm` 是一套基于 Spring Cloud 微服务架构的电商系统，采用了最新的技术栈（Spring Cloud 2023 + Spring Boot 3.2），提供完整的电商业务功能和微服务基础设施。

---

## 一、项目目录树结构

### 1. 根目录结构

```
mall-swarm/
├── .git/                           # Git版本控制目录
├── .idea/                          # IntelliJ IDEA配置目录
├── .vscode/                        # VS Code配置目录
├── config/                         # 配置中心配置文件目录
│   ├── admin/                      # 后台管理服务配置
│   │   ├── mall-admin-dev.yaml
│   │   └── mall-admin-prod.yaml
│   ├── demo/                       # 演示服务配置
│   │   ├── mall-demo-dev.yaml
│   │   └── mall-demo-prod.yaml
│   ├── gateway/                    # 网关服务配置
│   │   ├── mall-gateway-dev.yaml
│   │   └── mall-gateway-prod.yaml
│   ├── portal/                     # 前台商城服务配置
│   │   ├── mall-portal-dev.yaml
│   │   └── mall-portal-prod.yaml
│   └── search/                     # 搜索服务配置
│       ├── mall-search-dev.yaml
│       └── mall-search-prod.yaml
├── document/                       # 项目文档目录
│   ├── docker/                     # Docker相关配置
│   │   ├── docker-compose-app.yml
│   │   ├── docker-compose-env.yml
│   │   └── nginx.conf
│   ├── elk/                        # ELK日志系统配置
│   │   ├── logback-spring.xml
│   │   └── logstash.conf
│   ├── k8s/                        # Kubernetes部署配置
│   │   ├── mall-admin-deployment.yaml
│   │   ├── mall-admin-service.yaml
│   │   ├── mall-auth-deployment.yaml
│   │   ├── mall-auth-service.yaml
│   │   ├── mall-gateway-deployment.yaml
│   │   ├── mall-gateway-service.yaml
│   │   ├── mall-monitor-deployment.yaml
│   │   ├── mall-monitor-service.yaml
│   │   ├── mall-portal-deployment.yaml
│   │   ├── mall-portal-service.yaml
│   │   ├── mall-search-deployment.yaml
│   │   └── mall-search-service.yaml
│   ├── mind/                       # 思维导图文件
│   │   ├── app.emmx
│   │   ├── cms.emmx
│   │   ├── home.emmx
│   │   ├── oms.emmx
│   │   ├── pms.emmx
│   │   ├── sms.emmx
│   │   └── ums.emmx
│   ├── pdm/                        # 数据库设计文件
│   │   ├── mall.pdb
│   │   └── mall.pdm
│   ├── pos/                        # 架构图文件
│   │   ├── 微服务系统架构图.pos
│   │   ├── 系统架构图.pos
│   │   ├── 项目开发进度图.pos
│   │   └── 业务架构图.pos
│   ├── reference/                  # 参考文档
│   │   ├── deploy_windows.md
│   │   ├── dev_flow.md
│   │   └── function.md
│   ├── resource/                   # 资源文件（图片等）
│   ├── sh/                         # Shell脚本
│   │   ├── mall-admin.sh
│   │   ├── mall-auth.sh
│   │   ├── mall-gateway.sh
│   │   ├── mall-monitor.sh
│   │   ├── mall-portal.sh
│   │   └── mall-search.sh
│   └── sql/                        # SQL脚本
│       └── mall.sql
├── mall-admin/                     # 后台管理服务模块
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   └── resources/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── mall-auth/                      # 认证授权服务模块
│   ├── src/
│   │   └── main/
│   ├── target/
│   └── pom.xml
├── mall-common/                    # 通用工具模块
│   ├── src/
│   │   └── main/
│   ├── target/
│   └── pom.xml
├── mall-demo/                      # 演示服务模块
│   ├── src/
│   │   ├── main/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── mall-gateway/                   # API网关服务模块
│   ├── src/
│   │   ├── main/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── mall-logistics/                 # 物流服务模块
│   ├── src/
│   │   └── main/
│   ├── target/
│   ├── BUG_REPORT.md
│   ├── INTERVIEW_GUIDE.md
│   ├── LEARNING_GUIDE.md
│   ├── pom.xml
│   └── PROJECT_SUMMARY.md
├── mall-mbg/                       # MyBatis Generator代码生成模块
│   ├── src/
│   │   └── main/
│   ├── target/
│   └── pom.xml
├── mall-monitor/                   # 监控中心服务模块
│   ├── src/
│   │   ├── main/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── mall-portal/                    # 前台商城服务模块
│   ├── src/
│   │   ├── main/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── mall-search/                    # 搜索服务模块
│   ├── src/
│   │   ├── main/
│   │   └── test/
│   ├── target/
│   └── pom.xml
├── spring-security-jwt-refactor/   # Spring Security JWT重构方案
│   ├── auth-server/                # 认证服务器
│   │   ├── dto/
│   │   ├── AuthController.java
│   │   ├── AuthService.java
│   │   ├── CustomUserDetailsService.java
│   │   └── SecurityConfig.java
│   ├── common/                     # 通用组件
│   │   ├── JwtAuthenticationToken.java
│   │   ├── JwtUtil.java
│   │   ├── pom-dependencies.xml
│   │   ├── SecurityConstants.java
│   │   └── UserPrincipal.java
│   ├── config/                     # 配置文件
│   │   └── application-jwt.yml
│   ├── gateway/                    # 网关配置
│   │   ├── GatewaySecurityConfig.java
│   │   ├── JwtReactiveAuthenticationManager.java
│   │   ├── JwtServerAuthenticationConverter.java
│   │   └── JwtServerAuthenticationEntryPoint.java
│   ├── resource-server/            # 资源服务器
│   │   ├── JwtAuthenticationEntryPoint.java
│   │   ├── JwtAuthenticationFilter.java
│   │   └── ResourceServerConfig.java
│   ├── bean-annotation-explanation.md
│   ├── migration-guide.md
│   ├── mybatisplus-config-issue.md
│   ├── original-gateway-analysis.md
│   ├── problem-answers.md
│   ├── problem.md
│   ├── README.md
│   └── spring-auto-configuration-explanation.md
├── .env                            # 环境变量配置
├── deps.txt                        # 依赖列表
├── LICENSE                         # 开源协议
├── pom.xml                         # Maven主配置文件
└── README.md                       # 项目说明文档
```

---

## 二、核心技术栈

### 2.1 基础框架

| 技术 | 版本 | 说明 |
|------|------|------|
| **Java** | 17 | 编程语言 |
| **Spring Boot** | 3.2.2 | 容器+MVC框架 |
| **Spring Cloud** | 2023.0.1 | 微服务框架 |
| **Spring Cloud Alibaba** | 2023.0.1.0 | 微服务框架（阿里巴巴） |

### 2.2 微服务组件

| 技术 | 版本 | 说明 |
|------|------|------|
| **Nacos** | - | 服务注册与配置中心 |
| **Spring Cloud Gateway** | - | API网关 |
| **OpenFeign** | - | 声明式服务调用 |
| **Spring Cloud LoadBalancer** | - | 负载均衡 |
| **Spring Boot Admin** | 3.2.2 | 微服务监控中心 |

### 2.3 安全认证

| 技术 | 版本 | 说明 |
|------|------|------|
| **Sa-Token** | 1.37.0 | 轻量级权限认证框架 |
| **Sa-Token JWT** | 1.37.0 | JWT集成 |
| **Sa-Token Redis** | 1.37.0 | Redis集成（Jackson序列化） |
| **Sa-Token Reactor** | 1.37.0 | 响应式编程支持 |

### 2.4 数据持久化

| 技术 | 版本 | 说明 |
|------|------|------|
| **MySQL** | 8.0.29 | 关系型数据库 |
| **MyBatis** | 3.5.16 | ORM框架 |
| **MyBatis-Plus** | 3.5.4.1 | MyBatis增强工具 |
| **MyBatis Generator** | 1.4.2 | 代码生成器 |
| **PageHelper** | 6.1.0 | 分页插件 |
| **Druid** | 1.2.9 | 数据库连接池 |

### 2.5 缓存与消息队列

| 技术 | 版本 | 说明 |
|------|------|------|
| **Redis** | 7.0 | 分布式缓存 |
| **RabbitMQ** | 3.10.5 | 消息队列 |
| **MongoDB** | 5.0 | NoSQL数据库 |

### 2.6 搜索引擎

| 技术 | 版本 | 说明 |
|------|------|------|
| **Elasticsearch** | 7.17.3 | 搜索引擎 |
| **Kibana** | 7.17.3 | 数据可视化 |
| **Logstash** | 7.17.3 | 日志收集 |

### 2.7 对象存储

| 技术 | 版本 | 说明 |
|------|------|------|
| **Aliyun OSS** | 2.5.0 | 阿里云对象存储 |
| **MinIO** | 8.4.5 | 开源对象存储 |

### 2.8 API文档

| 技术 | 版本 | 说明 |
|------|------|------|
| **Knife4j** | 4.5.0 | API文档生成工具（基于OpenAPI 3） |

### 2.9 日志与监控

| 技术 | 版本 | 说明 |
|------|------|------|
| **Logstash Logback Encoder** | 5.3 | 日志编码器 |
| **Spring Boot Actuator** | - | 应用监控 |

### 2.10 工具类库

| 技术 | 版本 | 说明 |
|------|------|------|
| **Hutool** | 5.8.16 | Java工具类库 |
| **Lombok** | 1.18.22 | 简化Java代码 |
| **Jakarta Validation** | 3.0.2 | 参数校验 |
| **JSQLParser** | 4.7 | SQL解析器 |

### 2.11 容器化与部署

| 技术 | 版本 | 说明 |
|------|------|------|
| **Docker** | - | 容器化技术 |
| **Kubernetes** | - | 容器编排平台 |
| **Docker Maven Plugin** | 0.43.3 | Docker镜像构建插件 |
| **Nginx** | 1.22 | 反向代理服务器 |
| **Jenkins** | - | CI/CD工具 |
| **Portainer** | - | Docker可视化管理 |

### 2.12 支付集成

| 技术 | 版本 | 说明 |
|------|------|------|
| **Alipay SDK** | 4.38.61.ALL | 支付宝支付SDK |

### 2.13 分布式事务

| 技术 | 版本 | 说明 |
|------|------|------|
| **Seata** | - | 分布式事务解决方案 |

---

## 三、模块说明

### 3.1 核心业务模块

| 模块 | 说明 | 端口 |
|------|------|------|
| **mall-admin** | 后台管理服务（商品、订单、会员等管理） | 8180 |
| **mall-portal** | 前台商城服务（用户购物、订单等） | 8185 |
| **mall-search** | 商品搜索服务（基于Elasticsearch） | 8181 |
| **mall-logistics** | 物流服务（物流信息管理） | - |

### 3.2 基础设施模块

| 模块 | 说明 | 端口 |
|------|------|------|
| **mall-gateway** | API网关（路由转发、鉴权） | 8201 |
| **mall-auth** | 认证授权中心（统一认证） | 8401 |
| **mall-monitor** | 监控中心（Spring Boot Admin） | 8101 |

### 3.3 工具模块

| 模块 | 说明 |
|------|------|
| **mall-common** | 通用工具类、通用配置、通用组件 |
| **mall-mbg** | MyBatis Generator代码生成模块 |
| **mall-demo** | 微服务远程调用测试服务 |

---

## 四、业务架构

### 4.1 业务模块划分

- **UMS（User Management System）** - 用户管理系统
- **PMS（Product Management System）** - 商品管理系统
- **OMS（Order Management System）** - 订单管理系统
- **CMS（Content Management System）** - 内容管理系统
- **SMS（Sales Management System）** - 营销管理系统

### 4.2 核心业务流程

1. **用户注册登录** → mall-auth → mall-admin/mall-portal
2. **商品浏览搜索** → mall-gateway → mall-search/mall-portal
3. **下单支付** → mall-portal → mall-admin → 支付宝SDK
4. **订单管理** → mall-admin → mall-logistics
5. **营销活动** → mall-portal → mall-admin

---

## 五、技术架构特点

### 5.1 微服务架构

- **服务注册与发现**：Nacos
- **配置中心**：Nacos Config
- **API网关**：Spring Cloud Gateway
- **服务调用**：OpenFeign
- **负载均衡**：Spring Cloud LoadBalancer
- **服务监控**：Spring Boot Admin

### 5.2 安全架构

- **认证方式**：Sa-Token + JWT
- **权限控制**：基于角色的访问控制（RBAC）
- **会话管理**：Redis存储
- **网关鉴权**：统一在Gateway层进行鉴权

### 5.3 数据架构

- **关系型数据库**：MySQL（主数据存储）
- **缓存层**：Redis（热点数据缓存）
- **搜索引擎**：Elasticsearch（商品搜索）
- **NoSQL**：MongoDB（日志、非结构化数据）
- **消息队列**：RabbitMQ（异步处理、削峰填谷）

### 5.4 日志架构

- **日志收集**：Logstash
- **日志存储**：Elasticsearch
- **日志展示**：Kibana
- **ELK完整方案**：实现分布式日志追踪

### 5.5 部署架构

- **容器化**：Docker
- **容器编排**：Kubernetes
- **CI/CD**：Jenkins
- **容器管理**：Portainer
- **反向代理**：Nginx

---

## 六、开发环境要求

### 6.1 必需软件

| 软件 | 版本 | 用途 |
|------|------|------|
| JDK | 17+ | Java开发环境 |
| Maven | 3.6+ | 项目构建工具 |
| MySQL | 5.7+ | 数据库 |
| Redis | 7.0+ | 缓存 |
| Nacos | 2.x | 注册中心/配置中心 |

### 6.2 可选软件

| 软件 | 版本 | 用途 |
|------|------|------|
| Elasticsearch | 7.17.3 | 搜索引擎 |
| Kibana | 7.17.3 | 日志可视化 |
| Logstash | 7.17.3 | 日志收集 |
| MongoDB | 5.0+ | NoSQL数据库 |
| RabbitMQ | 3.10.5+ | 消息队列 |
| Docker | 最新版 | 容器化部署 |

---

## 七、项目特色

### 7.1 技术亮点

1. **最新技术栈**：Spring Boot 3.2 + Spring Cloud 2023
2. **轻量级认证**：Sa-Token替代传统Spring Security OAuth2
3. **响应式编程**：Gateway采用WebFlux响应式编程
4. **代码生成**：MyBatis Generator + MyBatis-Plus
5. **API文档**：Knife4j自动生成OpenAPI 3.0文档
6. **容器化部署**：完整的Docker + K8s部署方案

### 7.2 业务特色

1. **完整电商业务**：涵盖商品、订单、会员、营销等核心模块
2. **前后台分离**：管理后台 + 移动端商城
3. **多端支持**：uni-app实现多端统一
4. **支付集成**：支付宝支付集成
5. **物流管理**：独立物流服务模块

### 7.3 文档完善

1. **完整的部署文档**
2. **详细的开发文档**
3. **思维导图**：业务模块思维导图
4. **数据库设计**：PDM数据库设计文件
5. **架构图**：系统架构图、业务架构图

---

## 八、Maven依赖管理

### 8.1 父POM配置

```xml
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>3.2.2</version>
</parent>
```

### 8.2 核心依赖版本

```properties
java.version=17
spring-boot.version=3.2.2
spring-cloud.version=2023.0.1
spring-cloud-alibaba.version=2023.0.1.0
mybatis-plus-boot-starter.version=3.5.4.1
sa-token.version=1.37.0
knife4j.version=4.5.0
hutool.version=5.8.16
```

### 8.3 模块依赖关系

```
mall-swarm (父模块)
├── mall-common (被所有业务模块依赖)
├── mall-mbg (被业务模块依赖)
├── mall-admin (依赖 mall-mbg)
├── mall-portal (依赖 mall-mbg)
├── mall-search (依赖 mall-mbg)
├── mall-gateway (依赖 mall-common)
├── mall-auth (依赖 mall-common)
├── mall-monitor (独立模块)
├── mall-demo (测试模块)
└── mall-logistics (依赖 mall-mbg)
```

---

## 九、配置中心结构

### 9.1 Nacos配置文件

所有配置文件存储在 `config/` 目录下，按服务划分：

- **开发环境**：`*-dev.yaml`
- **生产环境**：`*-prod.yaml`

### 9.2 配置文件内容

每个服务的配置文件包含：
- 数据源配置
- Redis配置
- MyBatis配置
- 日志配置
- 业务相关配置

---

## 十、Docker部署

### 10.1 Docker Compose配置

- **docker-compose-env.yml**：基础环境（MySQL、Redis、Nacos等）
- **docker-compose-app.yml**：应用服务

### 10.2 镜像构建

使用 `docker-maven-plugin` 自动构建镜像：

```xml
<plugin>
    <groupId>io.fabric8</groupId>
    <artifactId>docker-maven-plugin</artifactId>
    <version>0.43.3</version>
</plugin>
```

---

## 十一、Kubernetes部署

### 11.1 K8s资源文件

每个服务包含：
- **Deployment**：服务部署配置
- **Service**：服务暴露配置

### 11.2 部署顺序

1. 基础环境（MySQL、Redis、Nacos等）
2. 配置中心（Nacos Config）
3. 注册中心（Nacos Discovery）
4. 网关服务（mall-gateway）
5. 认证服务（mall-auth）
6. 业务服务（mall-admin、mall-portal等）
7. 监控服务（mall-monitor）

---

## 十二、前端技术栈

### 12.1 管理后台（mall-admin-web）

| 技术 | 说明 |
|------|------|
| Vue.js | 前端框架 |
| Vue Router | 路由管理 |
| Vuex | 状态管理 |
| Element UI | UI组件库 |
| Axios | HTTP客户端 |
| v-charts | 图表组件 |

### 12.2 移动端商城（mall-app-web）

| 技术 | 说明 |
|------|------|
| Vue.js | 前端框架 |
| uni-app | 多端统一开发框架 |
| Vuex | 状态管理 |
| mix-mall | 电商项目模板 |
| luch-request | HTTP请求框架 |

---

## 十三、数据库设计

### 13.1 数据库表分类

- **ums_*** - 用户管理相关表
- **pms_*** - 商品管理相关表
- **oms_*** - 订单管理相关表
- **cms_*** - 内容管理相关表
- **sms_*** - 营销管理相关表

### 13.2 SQL脚本位置

```
document/sql/mall.sql
```

---

## 十四、API文档访问

### 14.1 Knife4j文档

- **开发环境**：http://localhost:8201/doc.html
- **生产环境**：http://your-domain:8201/doc.html

### 14.2 文档特性

- OpenAPI 3.0规范
- 在线调试
- 接口分组
- 参数说明
- 响应示例

---

## 十五、监控与日志

### 15.1 Spring Boot Admin监控

- **访问地址**：http://localhost:8101
- **监控内容**：
  - 应用健康状态
  - JVM信息
  - 线程信息
  - HTTP请求追踪
  - 日志查看

### 15.2 ELK日志系统

- **Kibana访问**：http://localhost:5601
- **日志收集**：Logstash
- **日志存储**：Elasticsearch
- **日志展示**：Kibana

---

## 十六、项目启动顺序

### 16.1 基础环境启动

1. MySQL
2. Redis
3. Nacos
4. Elasticsearch（可选）
5. RabbitMQ（可选）
6. MongoDB（可选）

### 16.2 应用服务启动

1. **mall-monitor** - 监控中心
2. **mall-gateway** - API网关
3. **mall-auth** - 认证中心
4. **mall-admin** - 后台管理服务
5. **mall-portal** - 前台商城服务
6. **mall-search** - 搜索服务
7. **mall-logistics** - 物流服务

---

## 十七、端口分配

| 服务 | 端口 | 说明 |
|------|------|------|
| Nacos | 8848 | 注册中心/配置中心 |
| MySQL | 3306 | 数据库 |
| Redis | 6379 | 缓存 |
| Elasticsearch | 9200 | 搜索引擎 |
| Kibana | 5601 | 日志可视化 |
| RabbitMQ | 5672/15672 | 消息队列 |
| MongoDB | 27017 | NoSQL数据库 |
| mall-monitor | 8101 | 监控中心 |
| mall-admin | 8180 | 后台管理服务 |
| mall-search | 8181 | 搜索服务 |
| mall-portal | 8185 | 前台商城服务 |
| mall-gateway | 8201 | API网关 |
| mall-auth | 8401 | 认证中心 |

---

## 十八、Spring Security JWT重构方案

项目包含了一套完整的Spring Security JWT重构方案，位于 `spring-security-jwt-refactor/` 目录。

### 18.1 重构内容

- **认证服务器**（auth-server）：处理用户登录认证
- **资源服务器**（resource-server）：保护业务接口
- **网关鉴权**（gateway）：统一网关层鉴权
- **通用组件**（common）：JWT工具类、认证Token等

### 18.2 相关文档

- `bean-annotation-explanation.md` - Bean注解说明
- `migration-guide.md` - 迁移指南
- `mybatisplus-config-issue.md` - MyBatis-Plus配置问题
- `original-gateway-analysis.md` - 原网关分析
- `problem-answers.md` - 问题解答
- `spring-auto-configuration-explanation.md` - 自动配置说明

---

## 十九、学习资源

### 19.1 官方文档

- **项目文档**：https://cloud.macrozheng.com
- **视频教程**：https://cloud.macrozheng.com/video/
- **学习教程**：https://github.com/macrozheng/mall-learning
- **Spring Cloud教程**：https://github.com/macrozheng/springcloud-learning

### 19.2 在线演示

- **后台管理系统**：https://www.macrozheng.com/admin/index.html
- **前台商城系统**：https://www.macrozheng.com/app/

### 19.3 相关项目

- **mall**：单体版电商项目
- **mall-admin-web**：管理后台前端
- **mall-app-web**：移动端商城前端

---

## 二十、开源协议

**Apache License 2.0**

Copyright (c) 2018-2025 macrozheng

---

## 二十一、总结

mall-swarm 是一个功能完善、技术先进的微服务电商项目，具有以下特点：

✅ **技术栈先进**：Spring Boot 3.2 + Spring Cloud 2023  
✅ **架构完整**：涵盖注册中心、配置中心、网关、监控等完整微服务基础设施  
✅ **业务完善**：包含电商核心业务模块  
✅ **文档齐全**：提供完整的开发和部署文档  
✅ **部署灵活**：支持Docker和Kubernetes部署  
✅ **学习价值高**：适合学习微服务架构和电商业务  

---

**文档生成时间**：2025-11-02  
**项目版本**：1.0-SNAPSHOT  
**作者**：macrozheng
