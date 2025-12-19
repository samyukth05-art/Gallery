# Ex.08 Design of Interactive Image Gallery
# Date:17.12.2025
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
views.py
from django.shortcuts import render

def gallery(request):
    return render(request,'gallery.html')
```
```
urls.py
from django.contrib import admin
from django.urls import path
from galleryapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.gallery),
]
```
```
gallery.html
{% load static %}
<!DOCTYPE html>
<html>
<head>
    <title>Image Gallery</title>

    <style>
        body{
            margin:0;
            background: linear-gradient(to right, #0f2027, #203a43, #2c5364);
            font-family: Georgia, serif;
            color: #f5f5f5;
        }

        h1{
            text-align:center;
            margin:30px 0;
            letter-spacing:3px;
            color: #e0f7fa;
        }

        .gallery{
            display:flex;
            flex-wrap:wrap;
            justify-content:center;
            gap:40px;
            padding:40px;
            max-width:1200px;
            margin:auto;
        }
        .gallery a{
            text-decoration: none;
        }

        .gallery img{
            width: 320px;
            height: 230px;
            object-fit: cover;
            border-radius: 18px;
            box-shadow:0 12px 25px rgba(0,0,0,0.7);
            transition: transform 0.35s ease, box-shadow 0.35s ease;
            cursor:pointer;
        }

        .gallery img:hover{
            transform: scale(1.2);
            box-shadow:0 22px 45px rgba(0,255,255,0.6);
            z-index:10;
        }

        .Photo {
            position: fixed;
            top: 0; 
            left: 0;
            width: 100%; height: 100%;
            background: rgba(0,0,0,0.9);
            display: none;
            justify-content: center;
            align-items: center;
        }

        .Photo img {
            max-width: 90%;
            max-height: 80%;
            border-radius: 12px;
            box-shadow: 0 0 30px rgba(0,255,255,0.4);
        }

        .Photo:target {
            display: flex;
        }

        .close {
            position: absolute;
            top: 20px;
            right: 30px;
            color: #00e5ff;
            font-size: 34px;
            text-decoration: none;
        }
    </style>
</head>

<body>

<h1>CAR GALLERY</h1>

<div class="gallery">
    <a href="#img1"><img src="{% static 'Bentley.jpg' %}"></a>
    <a href="#img2"><img src="{% static 'bugatti.jpg' %}"></a>
    <a href="#img3"><img src="{% static 'ferrari.jpg' %}"></a>
    <a href="#img4"><img src="{% static 'lambho.jpg' %}"></a>
    <a href="#img5"><img src="{% static 'royce.jpg' %}"></a>
    <a href="#img6"><img src="{% static 'Zonda.jpg' %}"></a>
</div>

<div class="Photo" id="img1">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'Bentley.jpg' %}" alt="Photo 1">
</div>

<div class="Photo" id="img2">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'bugatti.jpg' %}" alt="Photo 2">
</div>

<div class="Photo" id="img3">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'ferrari.jpg' %}" alt="Photo 3">
</div>

<div class="Photo" id="img4">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'lambho.jpg' %}" alt="Photo 4">
</div>

<div class="Photo" id="img5">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'royce.jpg' %}" alt="Photo 5">
</div>

<div class="Photo" id="img6">
    <a href="#" class="close">&times;</a>
    <img src="{% static 'Zonda.jpg' %}" alt="Photo 6">
</div>

</body>
</html>

```
# OUTPUT:
![alt text](<Screenshot 2025-12-19 080841.png>)
![alt text](<Screenshot 2025-12-19 093645.png>)

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
