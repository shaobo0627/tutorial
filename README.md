# Getting Started

This readme will help you get accustomed to the tools that we use at ScottyLabs.
Our applications primarily are built with nodejs and python, and we use git
to collaborate together.

Here we'll get you started with git, Github, and nodejs.

# Getting Started With Git

Git is a program that coders use to save versions of files as they develop code.
It helps organize code and makes it easier to fix issues in code if they ever show up.
Go to [learngitbranching.js.org](http://learngitbranching.js.org/) It
is a very useful website to learn git. Try doing all the lessons up to the *ramping up* section.

## Installing Git

### Windows and Mac
The best way to install it is using Githubs own installer [here](https://desktop.github.com/)
This will install Github's visual tool to work with git as well as the git command line tool.

### Linux
come talk to me.

## getting your own git repo
Now that you know a little bit more about git, lets start working on your own git directory.

First, login/signup to Github, and press the fork button on this repo. Now you should have a repo called `[USERNAME]/tutorial` on Github.

### Cloning Your Repo

On your favorite terminal write:
```
$ git clone https://github.com/[USERNAME]/tutorial.git
$ cd tutorial
```

This will make a folder with all the stuff that was on this directory. We'll use that folder to work on the nodejs part of the tutorial.

# Getting Started With Nodejs

## Installing
Go to [nodejs.org](https://nodejs.org/) and download the `v6.11.3` version. This will install nodejs on to your computer. Now we can get started on making your first program in node. We'll try to make a website that shows these instructions.

## Setting up the Npm Directory
```
npm init
...
npm install express express-remarkable --save
```

Now in the folder make a file called `index.js` inside of it copy the following lines of code.
```
var express = require('express')
var remarkable = require('express-remarkable')
var app = express()

app.engine('md', remarkable(app));
app.set('views', '.');
app.set('view engine', 'md');

function sendWebpage(request, response) {
  response.render('README');
}

app.get('/', sendWebpage)

app.listen('3000', () => {
  console.log('server is now running');
  console.log('go to http://localhost:3000 to see the output')
})
```

## Running Your Website

Now to run your website, open up this tutorial folder on the command line and run:
```
node index.js
```
If you now go online to [http://localhost:3000/](http://localhost:3000/)
you'll see the site set up your computer. It should show all these instructions
in a very basic plain webpage. To stop the server, press `<Ctrl-C>` (the
control and c keys at the same time).

# Showing Off What You Did
Now that you got your website working on your repo.
Let's do some git magic and put it up on Github.
The following commands will add and commit your changes and push them to your
Github repository.
```
git add -A
git commit -m "[YOUR COMMIT MESSAGE]"
git push origin master
```
On Github, make a pull request which lets you send your version of the repo to me letting me know that you've completed the tutorial.

# Congrats, You're Done
If you want to learn more about git, play around in
[learngitbranching.js.org](http://learngitbranching.js.org/). You can also play
around with the nodejs file to see how things worked. **don't be afraid to ask
me questions if you're confused.**
