---
title: "Hello World"
date: 2022-07-17T15:14:05+07:00
draft: false
---
As I'm getting older it's harder for me to remember things while I realize there are more things I need to learn. Improving my memory is important. Jotting things down so that I can revise later is also a good alternative. 

{{< ahref href="https://go.dev/" txt="Go">}} is a powerful programming language, and has been my "main" programming language for a few years by the time this post is being written. I'm excited to learn {{< ahref href="https://gohugo.io" txt="Hugo">}}, and hopefully I can create something fun with it. In this post I am sharing a basic tutorial of creating a blog using Hugo, and deploy it to a github page. This is what I achieved in a 2-hour session (yeah, I know, you can probably finish this in less than 2 hours, I'm getting old and slow!) of reading Hugo documents and repeating trial-and-error.

The first thing to do, is to install Hugo. I'm gonna assume that you're using a Mac, and have already installed {{< ahref href="https://brew.sh" txt="brew">}}. Run this command in your terminal of choice.
```sh
$ brew install hugo
```
Verify hugo version by running `hugo version` in your terminal. At the moment of writting this post, I'm using __v0.101.0+extended__.

Now you can run this command to initiate a new hugo site repository in your current directory
```sh
$ hugo new site personal-blog
```
This command will create a new folder `personal-blog` in your current directory. Note that `personal-blog` will be the folder to host all the necessary assets of the site. You are free to use another name as you see fit. For the remaining of this tutorial I will keep refering to the site we're working on as `personal-blog`, but you should know what I'm talking about.

The next thing we're gonna do is to install another theme. The theme I'm choosing for this tutorial is <a href="https://themes.gohugo.io/themes/hugo-papermod" target="blank">PaperMod</a>. To do this, firstly you need to `cd` into `personal-blog` and init a new git repository, and then finally add a git submodule of the new theme. All these steps are illustrated in the following commands
```sh
$ cd personal-blog
$ git init
$ git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```
You should probably see a bunch of new files added to folder `personal-blog`. Next, you should open your config file located at `personal-blog/config.toml` and add a new line to specify the theme
```toml
theme = "PaperMod"
```

Our new blog is almost ready now! We're gonna add a sample post to our blog. As a tradition, we're gonna add a Hello World blog post. The command for this is as followed
```sh
$ hugo new posts/hello-world.md
```
You should realize that a new file created at `personal-blog/content/posts/hello-world.md`. This is the content file for our first blog post. Go ahead and open it in your favorite text editor, you will see something like this
```yml
---
title: "Hello World"
date: 2022-07-17T15:14:05+07:00
draft: true
---
```
You can update the file content to add a simple Hello World message to your audience like this
```yml
---
title: "Hello World"
date: 2022-07-17T15:14:05+07:00
draft: true
---

Hello World
```
Note that the `draft` status is set to __true__, which means it won't be visible by default. However, this is good enough to showcase our blog in the local environment by simply running the following command
```sh
$ hugo server -D
```
The `-D` parameter means we're publishing our drafts as well as the finished posts. You should see some build logs in your terminal that includes a URL to your local blog. For me, it's `http://localhost:1313/personal-blog/`. Open your favorite browser and access the link, you should be greeted with your new blog! It's really nice of Hugo to provide us live reload out of the box, which means you can change your first post content, and Hugo will rebuild the blog automatically. Go ahead and try changing `Hello World` into something else and see for yourself.

We have just finished setting up our new blog in our local machine, it's time we take a step further: deploying our blog to the internet so that we can share with other people. This tutorial is quite long already, so let's continue in [another blog post]({{< ref "/posts/hello-world-part-2.md" >}} "another blog post")!
