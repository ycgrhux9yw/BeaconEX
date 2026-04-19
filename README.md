<div align="center">

<img src="winres/ICON.png" alt="Logo" width="160" height="160">

# BeaconEX - 我们Minecraft也要有自己的[图吧工具箱](#)

[![GitHub release](https://img.shields.io/github/v/release/GongSunFangYun/BeaconEX?style=flat-square)]()
[![Downloads](https://img.shields.io/github/downloads/GongSunFangYun/BeaconEX/total?style=flat-square)]()
[![Stars](https://img.shields.io/github/stars/GongSunFangYun/BeaconEX?style=flat-square)]()
[![Forks](https://img.shields.io/github/forks/GongSunFangYun/BeaconEX?style=flat-square)]()
[![Issues](https://img.shields.io/github/issues/GongSunFangYun/BeaconEX?style=flat-square)]()
[![License](https://img.shields.io/github/license/GongSunFangYun/BeaconEX?style=flat-square)]()
![简体中文支持](https://img.shields.io/badge/简体中文-支持-ff8c00?style=flat-square&labelColor=ff8c00&color=ffd700)

</div>

## 项目简介

BeaconEX 是一个用 Go 语言编写的 Minecraft 服务器管理工具箱，集成了服务器状态查询、日志分析、NBT文件处理、RCON远程控制、世界文件备份与分析等多种功能。得益于 Go 语言的跨平台特性，BeaconEX 可以在 Windows、Linux、macOS 等多个操作系统上运行。

> **个人备注**：这是我用于学习 Go 语言网络编程和 NBT 格式解析的参考项目，主要关注 RCON 和服务器查询模块的实现方式。
>
> **学习进度记录**：RCON 模块已读完，服务器查询模块阅读中。NBT 编辑器部分留待后续研究。

## 核心特性

### 跨平台支持
- 基于 Go 语言开发，编译生成单一可执行文件
- 支持 Windows (7/10/11)、Linux、macOS、FreeBSD
- 支持 x86、x86_64、ARMv7、ARM64、RISC-V 等多种架构
- 无需安装依赖，开箱即用

### 主要功能模块
- **服务器查询**：自动识别 Java/基岩版，查询服务器状态、MOTD、玩家在线情况
- **Ping测试**：网络连通性测试，支持持续 Ping 模式，ICMP 不可用时自动降级 TCP
- **RCON远程控制**：通过 RCON 协议远程执行服务器指令，支持交互式 Shell
- **日志分析**：AI 辅助分析服务器日志，提取错误信息并给出解决方案
- **NBT文件处理**：查看 Minecraft NBT 格式数据（玩家存档、level.dat等）
- **NBT编辑器**：交互式 NBT 编辑器，支持增删改查，全面支持 Region 文件格式
- **启动脚本生成**：AI 根据需求生成优化的服务器启动脚本
- **热力图生成**：分析 playerdata 目录，生成玩家游玩时长热力图
- **世界分析**：扫描并统计世界文件信息，检测可能损坏的世界
- **DLL注入**：Windows 平台专用，将 DLL 注入 Minecraft 进程
- **服务器图标生成**：将图片转换为 64x64 的 server-icon.png
- **世界备份**：支持定时、循环备份世界文件

### 待实现特性
- [ ] 优化 world_backup 模块的输出（低优先级|不影响功能）
- [ ] 更新软件徽标（低优先级|闲的屁吃更新的）

**下列特性将会作为'重型特性'实现**

- [ ] 新特性：Mod管理
- [ ] 新特性：版本控制
- [ ] 新特性：工具链
- [ ] 新特性：零碎模块功能整合

## 编译指南

### 环境要求
- Go 1.16 或更高版本
- Git

### 获取源码
```bash
git clone https://github.com/GongSunFangYun/BeaconEX.git
cd BeaconEX
```

### 安装依赖
```bash
go mod download
```

### 编译项目

项目提供了编译脚本，会自动编译 Windows、Linux、macOS、FreeBSD 等多个平台的可执行文件，以及 Windows 平台的安装程序。

#### Windows 系统
双击运行 `build.bat` 或在命令行执行：
```batch
build.bat
```

#### Linux/macOS 系统
```bash
chmod +x build.sh
./build.sh
```

编译完成后，所有可执行文件会保存在 `build` 目录下。

### 编译产物

| 文件 | 平台 | 架构 | 说明 |
|------|------|------|------|
| `beaconex-windows-x86_64-v302.exe` | Windows | x86_64 | 主程序 |
| `beaconex-windows-x86-v302.exe` | Windows | x86 | 主程序 |
| `beaconex-windows-arm64-v302.exe` | Windows | ARM64 | 主程序 |
| `beaconex-linux-x86_64-v302` | Linux | x86_64 | 主程序 |
| `beaconex-linux-x86-v302` | Linux | x86 | 主程序 |
| `beaconex-linux-arm64-v302` | Linux | ARM64 | 主程序 |
| `beaconex-linux-armv7-v302` | Linux | ARMv7 | 主程序 |
| `beaconex-linux-riscv64-v302` | Linux | RISC-V | 主程序 |
| `beaconex-darwin-x86_64-v302` | macOS | Intel | 主程序 |
| `beaconex-darwin-arm64-v302` | macOS | Apple Silicon | 主程序 |
| `beaconex-freebsd-x86_64-v302` | FreeBSD | x86_64 | 主程序 |
