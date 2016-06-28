# Anisina

A simple responsive theme for hexo, with qiniu image cdn support. Ported from Hux Blog and Kaijun Blog.
[![Anisina](http://o7bkkhiex.bkt.clouddn.com/Anisina.png)](http://haojen.github.io/)

## Summary
    
- [General](#general)
- [Features](#features)
- [install](#install)
- [Quick start](#quick-start)
- [About](#about)
- [License](#license)

## General

- **Author** : Haojen Ma
- **Version** : 1.0.2
- **Compatibility** : Hexo 3 or later

## Features

- Fully responsive
- Qiniu images CDN support
- Custom wechat title images
- Duoshuo/Disqus comment system
- Google/Baidu analytics
- Widgets

### Install

1. Download

```bash
git clone https://github.com/unnamed42/hexo-theme-Anisina.git [path/to/hexo]/themes/Anisina
```

2. Install dependencies

```bash
npm install hexo-renderer-ejs hexo-renderer-stylus --save
```

I assume you have already installed `hexo-generator-category`, `hexo-generator-pagination`, `hexo-generator-feed`, `hexo-generator-tag`, `hexo-generator-archive`.

If you want to use word count, install `hexo-wordcount`; to use site search, install `hexo-generator-search`.

3. Modify `theme` enrty in `_config.yml` to enable this theme:

```YAML
theme: Anisina
```

4. Regenerate your blog

```bash
hexo clean && hexo generate && hexo deploy
```

## Settings

#### Navigator

```YAML
nav:
  - name: archive
    url: archives/index.html
    icon: fa-archive
  - name: tags
    url: tags/index.html
    icon: fa-tags
  - name: guestbook
    url: guestbook/index.html
    icon: fa-comment
  - name: about
    url: about/index.html
    icon: fa-user
```

Every entry will become a shortcut on the upper right corner of your blog. The `icon` name must exist in [Font Awesome](http://fontawesome.io/icons/). Don't forget to create the corresponding folder and `index.md` first. You can do it by:

```bash
hexo new page [page-name]
```

#### cdn-url

qiniu images cdn or others are supported. Before using, you need to set you own cdn images root path. 

1. set your cdn-url,in your own `_config.yml` , set `cdn-url` to your own path

```YAML
cdn-url: http://you-cdn.com/
```

2. update your images to cdn library

3. in post **front-matter** section, set your images name

```YAML
wechat-share: icon-wechat.png
#or
header-img: some-images.png
```

In the generated HTML code, `img src` or `background-url` will be set to `http://you-cdn.com/icon-wechat.png` or `http://you-cdn.com/header-img`, etc.

If you don't need cdn, just leave it empty. The default path is hexo's `source/img` folder.

#### clip-*

qiniu imageView2 API

`cdn-url` must be set before using. More information about qiniu imageView2 API, please [click here](http://developer.qiniu.com/code/v6/api/kodo-api/image/imageview2.html)

#### Analytics

Google Analytics and Baidu Tongji simple config:

```YAML
#Baidu Analytics**
ba_track_id: 4cc1f2d8f3067386cc5cdb626a202900

#Google Analytics
ga_track_id: 'UA-49627206-1'            # Format: UA-xxxxxx-xx
ga_domain: huangxuan.me
```
Just checkout the code offered by Google/Baidu, and paste it here, all the rest is already done for you.

#### Comment

This theme support both Disqus and Duoshuo as the third party discussion system.

```YAML
duoshuo_username: _short_name_
duoshuo_share: # true or false
# or
disqus_username: _short_name_
```

Just replace `_short_name_` with your Disqus or Duoshuo short name. You can use both at the same time.

You can turn off Duoshuo Share by setting `duoshuo_share` to `false`, but Share cannot be used with duoshuo system off.

#### Widgets

```YAML
# Set to true to use jQuery based off-line search
# This function requires hexo-generator-search
site_search: true

# Recent contents
list_categories: true
recent_posts: true
recent_comments: true

# If you want to show word count, set to true
# This function requires hexo-wordcount
word_count: true

# Links
friends:
  - title: friend1
    url: http://www.friend1.com
```

The settings are self-explaining enough.

#### Featured Tags

```YAML
featured-tags: true
featured-condition-size: 1 # A tag will be featured if the size of it is more than this condition value
```

#### Sidebar settings

```YAML
# Sidebar settings
sidebar: true
sidebar-about-description: "your description here"
sidebar-avatar: avatar-hux.jpg
```

This will be shown as a sidebar on wide-screen devices on the right side of your blog. Everything will disappear automatically when displayed on a mobile device, this is the so-called responsive design.

##### SNS Accounts

```YAML
weibo_username: 
zhihu_username: 
github_username: 
twitter_username: 
facebook_username: 
linkedin_username: 
googleplus_id: # something after your https://plus.google.com/u/0/
steam_id: # something after your https://steamcommunity.com/id/
qq_id: # You need to enable qq online state at http://shang.qq.com/v3/widget.html
tieba_id: 
```

We've provided many SNS settings as above. All of them will be shown as circle button inside your sidebar.

### Excerpt

Usually the first line of your main text will be cut as excerpt without written explicitly. Everything after `front-matter` and before `<!-- more -->` is excerpt of your post. You can choose whether to show it in your main text or not by setting `show_excerpt`:

```YAML
show_excerpt: false
```

### Post

A **front-matter** example of a post is shown below:
```YAML
---
layout: post
title: "Hola 2016"
subtitle: "hi, I'm haojen ma"
date: 2016-05-26 06:00
author: "Haojen Ma"
header-img: "img/post-default.jpg"
wechat-share: "icon_wechat.jpg"
tags: [Movies,Life]
---
```
#### Poetry

If your like poetry, you can try `poetry` layout, that will be cool!

```bash
hexo new poetry 'your-poetry-name'
```

A poetry demo
 
![poetry-demo](http://o7bkkhiex.bkt.clouddn.com/poetry-show.png)

#### Header-img

post header images.
if you don't have set ,this will use post default header images.

#### Custom wechat title images

```YAML
wechat-share: "icon_wechat.jpg"
```

when your share post to wechat moments , this post images will show here,
if you don't have set ,this will use post header images.

## About

- Give is a Star if you like , fork or jest clone to use ,
and also you can help me fix bugs and add new feature :)
- if you have any problem or requirement , just open an issue here and i will help you.
- thanks kaijun and hux.

## License

MIT
