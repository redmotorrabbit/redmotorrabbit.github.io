---
layout: post
title: Deploy Angular to GitHub Pages
published: true
---

Let's create a new Angular app using the [Angular CLI](https://cli.angular.io/). If you don't have it, you can install Angular CLI globally using NPM.

````shell
$ npm install -g @angular/cli
````

The **ng new** command is used to create an Angular app that works right out of the box. I'm calling it **metrictown** 'cause I want to use it to map a town(ton) of metrics.

````shell
$ ng new metrictown
````

Change the working directory to the app directory using **cd**

````shell
$ cd metrictown
````

Build the app using the Angular CLI command **ng build** with the options shown here:

````shell
$ ng build --prod --output-path docs --base-href YourGitHubProjectName
````

The name of my GitHub repo is **metrictown** so this is what my build command looks like.

````shell
$ ng build --prod --output-path docs --base-href metrictown
````

When the build is complete, make a copy of docs/index.html and name it docs/404.html.

````shell
$ cp docs/index.html docs/404.html
````

Commit your changes.

````shell
$ git add .

$ git commit -m "Build project"
````

Set the remote, verify and push your changes.

````shell
$ git remote add origin https://github.com/redmotorrabbit/metrictown.git
# Sets the new remote

$ git remote -v
# Verifies the new remote URL

$ git push -u origin master
# Pushes the changes in your local repository up to the remote repository 
````

On the GitHub project page, configure it to publish from the [docs folder](https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages#publishing-your-github-pages-site-from-a-docs-folder-on-your-master-branch).

You should see your Angular app deployed to GitHub Pages at `https://**<user_name>**.github.io/**<project_name>**`

Here's mine. <https://redmotorrabbit.github.io/metrictown/>



