markdown的图片保存到本地之后，如果更换位置了图片的位置，就会显示不出来

因此想找个方法保存到网络上

这里记录下使用

marktext + picgo + github

来把图片保存到github上



第一步：下载marktext （网站上都有）基本没问题，github准备好一个仓库



第二步：下载picgo

前提要下载node.js ，来使用npm命令 cnpm命令 

    打开cmd命令框，输入下面的命令

```shell
cnpm install picgo -g 
```

第三步：

检查一下picgo是否下载好了

命令:

```shell
where picgo
```

结果:

![](https://cdn.jsdelivr.net/gh/startergain/front-end-learn/test/WindowsTerminal_rtIWUIQ1wQ.png)

第四步：

设置picgo uploader参数

命令:

```shell
picgo set uploader
```

结果

![](https://cdn.jsdelivr.net/gh/startergain/front-end-learn/test/WindowsTerminal_DcNDkQeBz1.png)

按上下键选择github

之后会进行参数的输入

![](https://cdn.jsdelivr.net/gh/startergain/front-end-learn/test/WindowsTerminal_T62CGCJvWe.png)

这一步的<mark>问题</mark>

1.出现form_data丢失

原因是npm的某个module丢失而导致无法使用命令

解决

```shell
cnpm install form_data
```

form_data可以替换成对应丢失的module

2.自定义域名的正确与否，会关系到marktext能否显示图片，如图的参数

```
https://cdn.jsdelivr.net/gh/startergain/front-end-learn
https://cdn.jsdelivr.net/gh/用户名/仓库名
前面是为了能够加速进入github
```

3.token需要从github上获取,具体在右上角的设置中，develop keys中获取



第五步：设置好了picgo参数，需要试着上传

命令:

```shell
picgo upload 文件路径
```

可能报错404,这种问题是无法找到github对应的仓库地址了，要么是网络问题，要么参数给的有问题

401,token可能不对



第六步：在marktext中设置图片存储设置为picgo即可

需要注意marktext的图片必须先保存到本地才能插入进去


