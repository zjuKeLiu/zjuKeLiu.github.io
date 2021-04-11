# A Comprehensive Survey on Graph Neural Networks

## 总结

- [源文章](https://arxiv.org/abs/1901.00596)
- [翻译原文](https://blog.csdn.net/weixin_35479108/article/details/86308808?utm_source=app&app_version=4.5.7)
- 作者：Zonghan Wu, Shirui Pan, Member, IEEE, Fengwen Chen, Guodong Long, Chengqi Zhang, Senior Member, IEEE, Philip S. Yu, Fellow, IEEE
- 一句话总结：提供了GNN的分类方法，总结了目前现有的各种图网络架构，讨论了图神经网络在各个领域的应用，总结了现有算法在不同任务中的开源代码，并提出了领域的潜在研究方向。

## Abstract

&nbsp;&nbsp;&nbsp;&nbsp;近年来，深度学习彻底改变了很多机器学习任务，从图像分类，视频处理到语音识别，自然语言处理等，但是通常来说，这些任务的数据都是欧式数据。现实中，很多数据都是非线性的，不是欧式数据，因此被表示为数据之间复杂关系和相互依赖的图结构。

&nbsp;&nbsp;&nbsp;&nbsp;图数据的复杂性给现有的机器学习算法带来了重大挑战。最近，出现了许多关于扩展图数据的深度学习方法的研究。本文对图神经网络（GNNs）在数据挖掘和机器学习方面的应用做了全面概述。提出一种新的分类方法对GNNs各种方法进行分类。着眼于图卷积网络(GCN),回顾了一些最近提出来的新的架构，包括Graph attention networks（图注意力网络），Graph autoencoders（图自编码），Graph generative networks（图生成网络）以及Graph spatial-temporal networks（图时空网络）。

&nbsp;&nbsp;&nbsp;&nbsp;另外，进一步讨论了图神经网络在各个领域的应用，总结了现有算法在不同任务中的开源代码，并提出了领域的潜在研究方向。

## Introduction

&nbsp;&nbsp;&nbsp;&nbsp;神经网络近期的成功推动了模式识别和数据挖掘的研究，许多机器学习任务，例如目标检测，机器翻译，语音识别，曾经都严重依赖棘手的特征工程提取数据集的特征，现在已经被端到端的学习模式彻底改变，也就是卷积神经网络（CNN），长短时记忆网络（LSTM），和自编码（AE）。深度学习在许多领域的成功部分归功于快速发展的计算资源(如GPU)和大量训练数据，部分归功于深度学习从欧氏数据(如图像、文本和视频)中提取有效的数据表示。以图像分析为例，图像为欧式空间的规则表示，CNN能够利用图像数据的平移不变性，局部连结性和组合性，也就是CNN能够为各种图像分析任务提取整个数据集共享的局部特征。