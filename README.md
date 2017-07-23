# Kyrgyz OCR

This is a modifiied clone of the "Secret Harbor" app.
The original app is located here:

https://github.com/matteotiziano/secret-harbor

Kyrgyz-OCR is a Heroku app using [Tesseract OCR](https://code.google.com/p/tesseract-ocr/) written in Python and based on the [Flask web microframework](http://flask.pocoo.org/). It works only for Englsh and Kyrgyz languages. 
You can add new languages by modifying the...

## Quick Start - Push the Button!

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Configuration
In addition to the default [heroku-buildpack-python](https://github.com/heroku/heroku-buildpack-python), this app also requires the custom [heroku-buildpack-tesseract](https://github.com/sitalk/heroku-buildpack-tesseract-kir).  

Heroku natively supports [multiple buildpacks per app](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app).

Before deploying the app, you should setup the base buildpack and add the custom buildpack to the app configuration:
```
heroku buildpacks:set heroku/python
heroku buildpacks:add https://github.com/sitalk/heroku-buildpack-tesseract-kir
```

## How to use
Let us assume you have deployed this app in Heroku and you called it `your-heroku-app`.

The app provides a test client `https://your-heroku-app.herokuapp.com/test` and a REST method `https://your-heroku-app.herokuapp.com/process`: the client provides the input file (image or PDF), whereas the REST method returns a JSON object containing the OCR of the input.

This app is available at https://secret-harbor.herokuapp.com/test.

## Licence
MIT Licence. Copyright (c) 2015 Matteo Maggioni
