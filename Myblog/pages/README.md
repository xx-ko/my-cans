### 如何添加一篇文章?

在源码下的 `./pages/` 文件夹下, 除了 `./pages/jsons/` 文件夹外的任何一个位置, 包括子文件夹都可以放置 `Markdown` 文件.

首先, 在上述允许的位置上创建一个`Markdown`文件, 并保存,

之后到 `./pages/jsons/` 目录下创建一个 `json` 文件 或者是打开该目录下 **现有的** `json` 文件.

并对齐进行相应的更改.

`./pages/jsons/` 目录下的json文件结构应该以如下形式.
 

		{
		  "文章id": {
			"postTime": "发布时间",
			"postAuthor": "发布作者",
			"postTitle": "标题",
			"title": "标题",
			"postContent": "Markdown文件路径"
		  },
		  "文章id2": {
			"postTime": "发布时间2",
			"postAuthor": "发布作者2",
			"postTitle": "标题2",
			"title": "标题2",
			"postContent": "Markdown文件路径2"
		  },
		  "文章idn": {
			"postTime": "发布时间n",
			"postAuthor": "发布作者n",
			"postTitle": "标题n",
			"title": "标题n",
			"postContent": "Markdown文件路径n"
		  }
		}


然后访问博客链接因有如下格式

```
./post.html?JSON文件名=文章id
```

例如有如下 `A.json` 与 `文章.md`

```
./pages/jsons/A.json
./pages/文章/文章1.md
./pages/文章2.md
```

文件结构如下:

		{
		  "123": {
			"postTime": "发布时间",
			"postAuthor": "发布作者",
			"postTitle": "标题",
			"title": "文章1",
			"postContent": "./文章/文章1.md"
		  },
		  "234": {
			"postTime": "发布时间",
			"postAuthor": "发布作者",
			"postTitle": "标题",
			"title": "文章2",
			"postContent": "./文章2.md"
		  }
		}

那么文章1的访问链接为

```
./post.html?A=123
```

文章2的访问链接为

```
./post.html?A=234
```

**注意: 文章id不能用中文!**

### 如何修改恻边栏的近期文章?

![近期文章](./pages/img/1.png)

看到源码下的 `./js/pages/preview-post.json` 文件

这是一个 `列表` , 文件格式如下:

		[
		  {
			"title": "我是标题",
			"time": "我是修改时间",
			"url": "我是链接",
			"markdown": "我是一段文字, 这段文字将会以Markdown格式解析"
		  }
		]

这个文件可以增加列表中的数量, 如下


		[
		  {
			"title": "我是标题",
			"time": "我是修改时间",
			"url": "我是链接",
			"markdown": "我是一段文字, 这段文字将会以Markdown格式解析"
		  },
		  {
			"title": "我是标题2",
			"time": "我是修改时间2",
			"url": "我是链接2",
			"markdown": "我是一段文字, 这段文字将会以Markdown格式解析2"
		  }
		]
		
排列越前, 他在页面中显示的也就越前.

**链接格式为** `./post.html?JSON文件名=文章id`


### 如何修改 `文章索引` 侧边栏?

看到源码下的 `./js/pages/post-list.json` 文件

文件结构如下: 

		{
		  "postJsonList": [
			{
			  "name": "显示名称",
			  "link": "对应保存文章的json路径",
			  "arg": "对应保存文章的json文件名"
			}
		  ],
		  "maxItem": 5
		}
			
			
与 `近期文章` 相同, 也能并列多个, 可以进行如下修改

		{
		  "postJsonList": [
			{
			  "name": "显示名称",
			  "link": "对应保存文章的json路径",
			  "arg": "对应保存文章的json文件名"
			},
			{
			  "name": "显示名称"2,
			  "link": "对应保存文章的json路径2",
			  "arg": "对应保存文章的json文件名2"
			}
		  ],
		  "maxItem": 5
		}