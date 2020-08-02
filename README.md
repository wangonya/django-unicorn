# django-unicorn
The magical fullstack framework for Django. ✨

`django-unicorn` provides a way to use backend Django code and regular Django templates to create interactive experiences without investing in a separate frontend framework.

# Why?
Building server-side sites in Django with the ORM and template engine is so pleasant, but once you need more interactivity on the frontend, there is a lot more ambiguity. Should you build out an entire API in Django REST framework? Should you use React or Vue.js (or some) other frontend framework?

It seems like there should be an easier way to create interactive experiences.

# A note on beta software
`django-unicorn` is beta software and the API will likely change on the way to 1.0. All efforts will be made to include an easy upgrade path. 1.0.0 will signify that the API won't change until the next major release.

# Site
https://www.django-unicorn.com

# Demo
https://github.com/adamghill/django-unicorn/blob/master/demo.mp4

# Install
1. `git clone git@github.com:adamghill/django-unicorn.git`
1. `pip install -e ../django-unicorn`
1. Add `django_unicorn` and `unicorn` to `INSTALL_APPS` in your Django settings file
1. Add `path("unicorn/", include("django_unicorn.urls")),` into your project's `urlpatterns` in `urls.py`
1. Add `{% load unicorn %}` to the top of your base template file
1. Add `{% unicorn_styles %}` and `{% unicorn_scripts %}` into your base HTML file

# How to create a component
1. `python manage.py startunicorn hello-world`
1. Add `{% unicorn 'hello-world' %}` into the template you want to load the new `hello-world` component
1. Take a look at `hello_world` class and `hello-world.html` template

# Current functionality
- `unicorn_styles`, `unicorn_scripts`, `unicorn` template tags
- Base `component` class
- Handles text input, checkbox, select options, select multiple options

# Developing
1. `git clone git@github.com:adamghill/django-unicorn.git`
1. `poetry install`
1. `poetry run example/manage.py migrate`
1. `poetry run example/manage.py runserver 0:8000`
1. Go to `localhost:8000` in your browser
1. To install in another project `pip install -e ../django-unicorn`

# Minify Javascript
1. `npm install`
1. `npm run-script build`

# Bump version
1. `npm run-script build`
1. `poetry version major|minor|patch`
1. Tag/commit/push version bump
1. `poetry publish --build -r pypi -u __token__`
