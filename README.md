tinygraphs
==============

**tinygraphs** is an avatar generator web service.

Contributors
=============

* [Santiago](https://github.com/santiaago)
* [Remy](https://github.com/rjourde)

How to use:
======

You can set the HTML source of the image to point directly to **tinygraphs.com** or you can save the image and use it directly on your site (*just remember to give us credit with a link to tinygraphs.com ;)* ).

        <img src="http://tinygraphs.com/checkerboard">

## parameters:

### size:

`tinygraphs.com/squares/hello?size=60`

### formats
The default format is `JPEG`.

Supported formats are:
* JPEG
* SVG

`tinygraphs.com/squares/hello?fmt=svg`


### background and foreground:
You can specify the color of the background or foreground by using parameters `bg` and `fg` and passing an hexadecimal value of the color:

`tinygraphs.com/squares/hello?bg=ff4008&fg=04d6f2`

## Supported routes:

`http://tinygraphs.com/checkerboard`

![checkerboard](http://tinygraphs.com/checkerboard?size=120)

`http://tinygraphs.com/squares/anything`

![squares](http://tinygraphs.com/squares/anything?size=120)

`http://tinygraphs.com/squares/random`

![random](http://tinygraphs.com/squares/random?size=120)


Organization
=====

Lets start with a milestone each 2 weeks for now.

Stack
======

* Go
* mongodb
* heroku

Installation
======

*   `cd $GOPATH/src`
*   `go get github.com/taironas/tinygraphs`
*   `cd $GOPATH/src/github.com/tinygraphs`
*   `go get ./app-backend`
*   `export PORT=8080`

Run App
=======

    > pwd
    $GOPATH/src/github.com/taironas/tinygraphs
    > app-backend
    2014/11/19 22:23:57 Listening on 8080

Build
======
    >cd $GOPATH/src/github.com/tinygraphs
    >go get ./app-backend

Test locally
=============
**option 1:**

    > app-backend
    2014/12/07 00:35:02 Listening on 8080

**option 2:**

If you have heroku install you should be able to run

    > foreman start
    00:37:38 web.1  | started with pid 5762
    00:37:38 web.1  | 2014/12/07 00:37:38 Listening on 8080

Deploy
=======

**Note:** heroku is now configured to build and deploy any `git push`to `master`. If you still want to manual deploy the app follow the steps below.

Before you start be sure to have the proper rsa key. [See Managing Your SSH Keys](https://devcenter.heroku.com/articles/keys) for more details and that. Also be sure to be logged in with heroku.

    > heroku login
    Enter your Heroku credentials.
    Email: ga@tinygraphs.com
    Password:

After that you can deploy as follows:

    > git push heroku master
    Fetching repository, done.
    Counting objects: 5, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 287 bytes | 0 bytes/s, done.
    Total 3 (delta 2), reused 0 (delta 0)

    -----> Fetching custom git buildpack... done
    -----> Go app detected
    -----> Using go1.3
    -----> Running: go get -tags heroku ./...
    -----> Discovering process types
           Procfile declares types -> web

    -----> Compressing... done, 1.5MB
    -----> Launching... done, v6
           https://tinygraphs.herokuapp.com/ deployed to Heroku

    To git@heroku.com:tinygraphs.git
       56a3000..5572085  master -> master
