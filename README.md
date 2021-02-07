# [superset](https://github.com/apache/incubator-superset) 1.0.0 on [Heroku](http://heroku.com)

Superset is a data exploration platform designed to be visual, intuitive, and interactive. Visit the project's website at <http://airbnb.io/superset>

Updated and working as of Feb 5, 2021

## Deploying on Heroku

To get your own Superset 1.0.0 App running on Heroku, click the button below:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/turquoisehealth/superset-on-heroku)

To finish configuration, you need the [Heroku Toolbelt](https://toolbelt.heroku.com/) installed.

After deploying, you need to set the FLASK_APP environment variable or the app won't work:

```
heroku config:set FLASK_APP=superset --app YOURAPPNAME
```

Then, you need to initialize the database and create the first user:

```
heroku run bash --app YOURAPPNAME
superset db upgrade
superset init
fab create-admin --app superset
exit
```

After this, Superset will be accessible at `YOURAPPNAME.herokuapp.com`.

