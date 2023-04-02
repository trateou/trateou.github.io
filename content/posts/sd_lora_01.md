---
title: "Stable Diffusion + Lora 的初体验01" 
date: 2023-04-02T11:29:36+08:00 
# weight: 1
tags: ["first"]
author: "Milliways"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Desc Text."
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

大家好,今天给大家分享下stable diffusion webui(下列均使用sd替代) + lora的使用体验.

## 背景

本文面向读者为有一定动手,信息检索能力的玩家.

由于篇幅限制,本文不展开介绍sd的安装.侧重介绍lora模型以及如何查找合适lora模型,以及使用对应的模型

详细信息请查阅:[stable diffusion的安装](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

另外:本文需要读者拥有科学上网环境,因为某些网站需要代理访问

因为时间仓促,写得比较简单,本文可能后续会继续更新.

## 作者

​	miiliways,欢迎加v:`0xfffo` ,一起在群里聊天,讨论技术

![image-20230402124818484](/image-20230402124818484.png)

## 开发环境:

win11 + wsl2(ubuntu)+rtx系列显卡

## lora介绍

Lora(Low-Rank Adaptation of Large Language Models)模型是通过制定少量图片经过训练构成的小模型，可以和大模型结合使用，干涉大模型产生的结果。



## 安装

安装基础lora模型

1.下载基础模型

https://huggingface.co/swl-models/chilloutmix-ni/blob/main/chilloutmix-Ni.safetensors

![image-20230402120337723](/image-20230402120337723.png)

下载完毕后得到chilloutmix.satetensors

把这个文件放置在stable-diffusion-webui/models/Stable-diffusion/下

2.下载lora调整模型

这里我推荐这个网站,全世界各地网友把自己训练的模型,上传到这里[[Civitai](https://civitai.com/)](https://civitai.com)

![image-20230402120547719](/image-20230402120547719.png)

这里我们随便找一个lora进行测试[Cute_girl_mix4 | Stable Diffusion LORA | Civitai](https://civitai.com/models/14171/cutegirlmix4)

![image-20230402120957925](/image-20230402120957925.png)

这里下载这个模型(cuteGirlMix4_v10.sadetensors)后,把它放到stable-diffusion-webui/models/lora/下

## 启动sd webui

### 选择指定基础模型

![image-20230402122756081](assets/image-20230402122756081.png)

### 生成图片

这里为了方便,我们直接使用页面上的推荐参数,并且填写到我们自己的页面对应位置上

![image-20230402122858472](/image-20230402122858472.png)

这里我们看到的是,生成的图像(右边)和原图相比并不是非常一致,这里笔者怀疑是由于我们的基础模型不一样导致的

![image-20230402123401606](assets/image-20230402123401606.png)

这里要注意的一点是,页面上<lora:mix4:0.5> 要改成<lora:cuteGirlMix4_v10:0.5>,这里规则为\<lora:model_name:weight\>

model_name即为我们刚才下载的cuteGirlMix4_v10. weight为参考模型权重

![image-20230402123556241](/image-20230402123556241.png)



## 结尾

其实我们可以看到生成一张图片现在已经非常简单了.

1.下载stable diffusion

2.下载基础模型

3.下载lora模型

4.填写prompt

5.生成图片

后续笔者考虑会出一个桌面程序,支持程序内直接支持lora模型选择,下载等.方便大家的操作.





## 彩蛋时间🥳

关于生成福利图片

就以刚才的lora页面为准.[Cute_girl_mix4 | Stable Diffusion LORA | Civitai](https://civitai.com/models/14171/cutegirlmix4)

下面有一堆网友评论,

![image-20230402124608267](/image-20230402124608267.png)

大家可以选择对应喜欢图片的prompt,尝试去生成,修改.

![image-20230402124618643](/image-20230402124618643.png)
