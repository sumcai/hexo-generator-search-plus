
Modify from [hexo-generator-search-minify](https://www.npmjs.com/package/hexo-generator-search-minify)

Remove code area and all html tag in generated XML file and fix the issue that permalink contains `\\`.

在原始版本上做了以下一些修改：

1. 生成的 XML 文件 content 部分去掉了代码及 HTML Tag，这有助于减小文件体积，且可以提高搜索时的准确度；
2. 修复文章的`Front-matter` 中设置固定路径 `permalink`时url中出现`\\`的问题。



## Install

``` bash
$ npm install hexo-generator-search-plus --save
```

## Options

You can configure this plugin in your root `_config.yml`. Default configuration:

``` yaml
search:
  path: search.xml
  field: post
  content: true
  template: ./search.xml
```

- **path** - file path. By default is `search.xml` . If the file extension is `.json`, the output format will be JSON. Otherwise XML format file will be exported.
- **field** - the search scope you want to search, you can chose:
  * **post** (Default) - will only covers all the posts of your blog.
  * **page** - will only covers all the pages of your blog.
  * **all** - will covers all the posts and pages of your blog.
- **content** - whether contains the whole content of each article. If `false`, the generated results only cover title and other meta info without mainbody. By default is `true`.
- **template** (Optional) - path to a custom XML template

