---
title: "示例文章标题"
date: 2018-08-08 08:08:08 +0800
category: Demo example
tags: [Minimalism, Demo]
comment: false
reward: false
excerpt: 这是这篇文章的摘要，或者你也可以在文章正文中使用 <!--more--> 标签来截断摘要。
---

### 创建一个新的bolg文件
./new test_for_it

### c/c++ 调试

#### 配置cpp文件
使用F1，打开命令选项，输入C/C++，选择C/C++:Edit configuration，生成c_cpp_properties.json配置文件
```json
{
    "configurations": [
        {
            "name": "Linux",
            "includePath": [
                "${workspaceFolder}/**"
            ],
            "defines": [],
            "compilerPath": "/usr/bin/gcc",
            "cStandard": "c11",
            "cppStandard": "c++17",
            "intelliSenseMode": "clang-x64"
        }
    ],
    "version": 4
}
```
#### 生产launch.json配置文件
在debug界面中选择添加配置，然后选择才c++(gdb/lgdb)选项，生成launch.json 顾名思义此文件主要服务于调试时的加载控制
```json
{
    // 使用 IntelliSense 了解相关属性。
    // 悬停以查看现有属性的描述。
    // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
    "version": "0.2.0",
    "configurations": [

        {
            "name": "(gdb) 启动",
            "type": "cppdbg",
            "request": "launch",
            "program": "${workspaceFolder}/${fileBasenameNoExtension}",
            "args": [],
            "stopAtEntry": false,
            "cwd": "${workspaceFolder}",
            "environment": [],
            "externalConsole": false,
            "MIMode": "gdb",
            "preLaunchTask": "build",
            "setupCommands": [
                {
                    "description": "test",
                    "text": "-enable-pretty-printing",
                    "ignoreFailures": true
                }
            ]
        }
    ]
}
```

####  配置task.json配置文件
在命令窗口中输入task，选择task： configure task选项生成tasks.json文件
注意launch.json中的"preLaunchTask"调用与“label”相同的task
```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "build",
            "type": "shell",
            "command": "g++",
            "args":[
                "-g","${fileBasenameNoExtension}.cpp","-o","${fileBasenameNoExtension}"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
```

### atom 镜像网站
[淘宝npm镜像](http://npm.taobao.org/mirrors/atom/1.39.0-beta3/ "淘宝镜像")
