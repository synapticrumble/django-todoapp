# Creating a Django ToDo App based on Dennis Ivy Course

This is a project to create a todo app using python. It's ready to go so you can just clone and start running the app!

## Configuring SECRET_KEY for production environment

1. Setup a new secret environment variable where the key is `SECRET_KEY` and the value is
   a randomly generated token. To generate such a token type this into the shell and hit Enter:
```python
$ echo "export SECRET_KEY='$(openssl rand -hex 40)'" > .DJANGO_SECRET_KEY
$ source .DJANGO_SECRET_KEY

```
2. On your project's settings.py file add these lines of code:

```python
import os

# ...

try:
    SECRET_KEY = os.environ["SECRET_KEY"]
except KeyError as e:
    raise RuntimeError("Could not find a SECRET_KEY in environment") from e
    
```

## Installing packages

To add packages to your project, you can just install packages directly from the file requirements.txt after creating a virtual environment, and activate the virtual environment before installing packages. On your project folder, use the below shell scripts provided
(for Windows environment, Linux environment will be slightly different!):
```shell
>virtualenv .env
>.env\Scripts\activate
>pip install -r requirements.txt
>python manage.py makemigrations
>python manage.py migrate
>python manage.py runserver
```

## Help

If you need help you might be able to find an answer on youtube by searching for "django-todoapp Dennis Ivy"
