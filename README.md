[![Build Status](https://travis-ci.com/jgraph/drawio.svg?branch=master)](https://travis-ci.com/jgraph/drawio)

About
-----
[diagrams.net](https://app.diagrams.net), [previously draw.io](https://www.diagrams.net/blog/move-diagrams-net), is an online diagramming web site that delivers the source in this project.

License
-------
The source code in this repo is licensed under the Apache v2.

Development
-----------

Note: We cannot accept non-trivial PRs for legal reasons. We need to retain copyright over the entire codebase.

A development guide is being started on the GitHub project wiki. There is a [draw.io](http://stackoverflow.com/questions/tagged/draw.io) tag on Stack Overflow currently, please make sure any questions adhere to their guidelines for questions.

The [mxGraph documentation](https://jgraph.github.io/mxgraph/) provides a lot of the docs for the bottom part of the stack. There is an [mxgraph tag on SO](http://stackoverflow.com/questions/tagged/mxgraph).

Building
-------
In etc/build, run `ant war` will package in draw.war.

Running
-------
One way to run diagrams.net is to fork this project, [publish the master branch to GitHub pages](https://help.github.com/categories/github-pages-basics/) and the [pages sites](https://jgraph.github.io/drawio/src/main/webapp/index.html) will have the full editor functionality (sans the integrations).

Another way is to use [the recommended Docker project](https://github.com/jgraph/docker-drawio) or to download [draw.io Desktop](https://get.diagrams.net).

The full packaged .war of the client and servlets is built when the project is tagged and available on the [releases page](https://github.com/jgraph/draw.io/releases), run place draw.war in webapps in tomcat, run on https://127.0.0.1:8080/draw/

Supported Browsers
------------------
diagrams.net supports IE 11, Chrome 70+, Firefox 70+, Safari 11+, Opera 50+, Native Android browser 7x+, the default browser in the current and previous major iOS versions (e.g. 11.2.x and 10.3.x) and Edge 79+.


## 模型构建属性设置
### 全局参数
![proj_config](image/proj_config.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>projectName</th>
            <th>项目名称</th>
            <th>字母数字组合且起始不为数字</th>
            <th>否</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>version</th>
            <th>项目版本</th>
            <th>x.y.z形式,x表示主版本号,y表示次版本号,z表示修订号</th>
            <th>否</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>target</th>
            <th>目标架构</th>
            <th>神经网络运行硬件平台</th>
            <th>是</th>
            <th>darwinII/darwinIII</th>
            <th>darwinII</th>
        </tr>
    </table>

注：


### 输入节点
![input_node](image/input_node.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>layerName</th>
            <th>输入节点名</th>
            <th>字母数字组合且起始不为数字</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>encodingType</th>
            <th>编码格式</th>
            <th>支持的编码格式</th>
            <th>否</th>
            <th>poisson/latency</th>
            <th>poisson</th>
        </tr>
        <tr>
            <th>neuronsize</th>
            <th>神经元数量</th>
            <th>仅正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
    </table>

注：输入层神经元数量需要和输入数据格式对应，否则会出错（如输入为28*28的图片，则神经元数量必须为784）。目前无法自动确定，需要用户手动填写。


### 隐藏层
![hidden_layer](image/hidden_layer.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>layerName</th>
            <th>层名</th>
            <th>字母数字组合且起始不为数字</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>neuronsize</th>
            <th>神经元数量</th>
            <th>仅正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>neuronType</th>
            <th>神经元类型</th>
            <th>预先定义好的神经元模型名</th>
            <th>是</th>
            <th>clif/lif/if/izh</th>
            <th>clif</th>
        </tr>
        <tr>
            <th>leakSign*</th>
            <th>脉冲衰减</th>
            <th>脉冲经过神经网络是否衰减,YES:衰减，NO:不衰减</th>
            <th>是</th>
            <th>YES/NO</th>
            <th>YES</th>
        </tr>
        <tr>
            <th>leakValue*</th>
            <th>馈电值</th>
            <th>仅正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>resetMode*</th>
            <th>神经元电位重置方式</th>
            <th>仅正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>vThreshold</th>
            <th>阈值电压(mV)</th>
            <th>仅正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
    </table>

注：标记“*”的脉冲衰减、馈电值和神经元电位重置方式属性，目前需要在snnflow代码中构建并注册神经元模型时就确定(如下图，IF神经元由4条运算规则定义)。用户在选择神经元类型后，这三个属性已经可以确定下来，此处的配置会在后续写入到MDL中，影响仿真和编译，但不会对训练产生影响。

![neuron_def_IF](image/neuron_def_IF.png?raw=true)

### 输出节点
![output_node](image/output_node.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>layerName</th>
            <th>输出节点名</th>
            <th>字母数字组合且起始不为数字</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>decodingtype</th>
            <th>解码格式</th>
            <th>支持的解码格式</th>
            <th>否</th>
            <th>spike_counts</th>
            <th>spike_counts</th>
        </tr>
        <tr>
            <th>targetlayer</th>
            <th>目标网络层</th>
            <th>已存在的隐藏层名</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
    </table>

注：



### 连接配置
![connection](image/connection.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>link_type</th>
            <th>连接类型</th>
            <th>NA</th>
            <th>是</th>
            <th>full/sparse/conv</th>
            <th>full</th>
        </tr>
    </table>

注：目前训练器只支持full类型连接



### 训练参数
![train_param](image/train_param.png?raw=true)
<table>
        <tr>
            <th>属性名</th>
            <th>属性中文名</th>
            <th>规则</th>
            <th>是否必填</th>
            <th>可选值</th>
            <th>默认值</th>
        </tr>
        <tr>
            <th>runTime</th>
            <th>运行时长(ms)</th>            
            <th>正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>batchsize</th>
            <th>每批数量</th>
            <th>正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>epochnum</th>
            <th>训练代数</th>
            <th>正整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>trainingplatform</th>
            <th>训练平台</th>
            <th>NA</th>
            <th>是</th>
            <th>auto/cpu/gpu</th>
            <th>auto</th>
        </tr>
        <tr>
            <th>learningrate</th>
            <th>学习率</th>
            <th>非负数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
        <tr>
            <th>lrdecaystep</th>
            <th>学习率衰减周期</th>
            <th>非负整数</th>
            <th>是</th>
            <th>NA</th>
            <th></th>
        </tr>
    </table>

注：