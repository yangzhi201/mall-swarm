# 项目架构总结

## 模块划分
项目分为多个子模块，包括：
- **mall-common**：通用模块，提供工具类和基础功能。
- **mall-mbg**：代码生成模块。
- **mall-admin**：后台管理模块。
- **mall-search**：搜索模块。
- **mall-portal**：门户模块。
- **mall-monitor**：监控模块。
- **mall-gateway**：网关模块。
- **mall-auth**：认证模块。

每个模块独立开发，便于维护和扩展。

## 核心功能
### mall-common 模块
- 提供统一的 API 响应格式（`CommonResult`）。
- 定义 Redis 操作接口（`RedisService`），支持多种数据结构的操作。
- 包含异常处理、日志记录等通用功能。

### 其他模块
- **mall-admin**：提供后台管理相关的 API 和服务。
- **mall-search**：实现搜索功能的 API 和服务。
- **mall-portal**：提供门户功能的 API 和服务。

## 依赖管理
- 使用 Maven 进行依赖管理和构建。
- 集成 Spring Boot 和 Spring Cloud，支持微服务架构。
- 使用阿里云镜像加速依赖下载。

## 项目架构图
以下是一个简单的 Mermaid 图表，展示项目的主要模块及其关系：

```mermaid
graph TD
    A[mall-swarm] --> B[mall-common]
    A --> C[mall-mbg]
    A --> D[mall-admin]
    A --> E[mall-search]
    A --> F[mall-portal]
    A --> G[mall-monitor]
    A --> H[mall-gateway]
    A --> I[mall-auth]

    B --> J[CommonResult]
    B --> K[RedisService]
    B --> L[Exception Handling]
    B --> M[Logging]

    D --> N[Admin API]
    D --> O[Admin Service]

    E --> P[Search API]
    E --> Q[Search Service]

    F --> R[Portal API]
    F --> S[Portal Service]