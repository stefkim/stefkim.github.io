---
layout: post
title: "Archive"
permalink: /archive/
---

<section class="archive-post-list">

   {% for post in site.posts %}
       {% assign currentDate = post.date | date: "%Y" %}
       {% if currentDate != myDate %}
           {% unless forloop.first %}</ul>{% endunless %}
           <h3>{{ currentDate }}</h3>
           <ul>
           {% assign myDate = currentDate %}
       {% endif %}
       <li>
       <a href="{{ post.url }}">
       {{ post.title }} - 
       <span>{{ post.date | date: "%B %-d" }}</span>
        
        </a>
        </li>
       {% if forloop.last %}</ul>{% endif %}
   {% endfor %}

</section>