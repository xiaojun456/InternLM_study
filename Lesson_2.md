# 亮点
1.完成了基础和进阶作业

2.部署并测试多个样例，实验发现书生浦语大模型可以较好的完成多轮对话，但在较复杂的推理问答中还有提高的空间

3.浦语·灵笔2可以进行较丰富的图文创作，会有幻觉问题，回答问题有时不够贴切。

整体来说， InternLM2-Chat-1.8B已经可以进行较为流畅的对话，能够进行基本的问答操作

# 概述
教学视频：https://www.bilibili.com/video/BV1AH4y1H78d/

文档链接：https://github.com/InternLM/Tutorial/blob/camp2/helloworld/hello_world.md

# 过程要点
## 配置基础环境
选择镜像 用 Cuda11.7-conda 镜像
```
studio-conda -o internlm-base -t demo
# 与 studio-conda 等效的配置方案
# conda create -n demo python==3.10 -y
# conda activate demo
# conda install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.7 -c pytorch -c nvidia
```

# 实验结果
## 使用 InternLM2-Chat-1.8B 模型生成 300 字的小故事
 InternLM2-Chat-1.8B生成的故事逻辑清晰，流程，还有转折，结果非常符合正能量
 ![2024-06-02_114332](https://github.com/xiaojun456/InternLM_study/assets/156819467/ebabb2cd-f318-451f-93d2-69b3f9f67301)
 

## 使用书生·浦语 Web 和浦语对话
能实现简单的对话问答，但是稍复杂一些的推理就有所欠缺了，详细见上图。在我第一次询问赞比亚属于哪个洲时，他无法根据前一句话去推理回答，但是当我直接问问题的时候，则可以回答， 因此对于多轮对话的理解还是稍显不足。
## 部署八戒-Chat-1.8B 模型并对话
八戒--Chat-1.8B 模型能够很好的扮演八戒的角色进行拟人对话，效果很好，生成速度也很快
![2024-06-02_114311](https://github.com/xiaojun456/InternLM_study/assets/156819467/b27c9f6c-4312-4cc2-8c86-fe8d71958535)

## 完成浦语·灵笔2的图文创作及视觉问答部署
### 图文创作
对于给定实例的图文创作，结果还是不错的，能够输出紧密联系标题的文字和图片。
![2024-06-02_123550](https://github.com/xiaojun456/InternLM_study/assets/156819467/6f6bfc57-d296-4f12-9372-824e9f3630e7)
但对于第二个样例，我让他生成图片和文字时，有一些文不切题，生成的图片和文字更像是一些拼凑，可能是我输入的材料并非主流语料库中的材料，也存在一些幻觉问题
![2024-06-02_123550](https://github.com/xiaojun456/InternLM_study/assets/156819467/ffcdb4a7-cb32-4e84-8c67-297924fd7c2a)
![2024-06-02_125128](https://github.com/xiaojun456/InternLM_study/assets/156819467/84993ba0-68f5-4c96-a41c-7c12abe0fd11)


### 视觉问答
图为名侦探柯南动漫的截图，灵笔能识别出是动画截图，但是识别人数错误，而且对于关系的判定也是错误的，可能是因为动画领域的语料和图片知识还没有特别多的输入。
能够准确分辨出人物，风景和建筑。
![2024-06-02_130236](https://github.com/xiaojun456/InternLM_study/assets/156819467/3171d2bc-24c5-4233-9732-6d6a353bf8b2)

## Lagent工具调用数据分析 Demo 部署
以 InternLM2-Chat-7B 作为基础模型，使用Lagent工具实现智能体。模型能代码解释器工具，编写python代码，但并没有直接给出答案，需要追问出结果
![2024-06-02_121744](https://github.com/xiaojun456/InternLM_study/assets/156819467/f3421d17-0ce0-4ec8-9040-d1d99621d445)

# 结语
熟悉了studio平台的使用，完成了几个demo部署。收获颇多







