# Azure_batch3
Demo


python -m venv .venv

source .venv/bin/activate

python -m pip install --upgrade pip setuptools wheel

python -m pip install django

django-admin startproject web_project

python manage.py migrate

python manage.py startapp hello


from django.http import HttpResponse

def home(request):
    return HttpResponse("Hello, Django!")


from django.urls import path
from hello import views

urlpatterns = [
    path("", views.home, name="home"),
]


from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("", include("hello.urls")),
    path('admin/', admin.site.urls)
]



