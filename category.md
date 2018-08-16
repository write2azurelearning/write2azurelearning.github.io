---
layout: page
permalink: /categories/
title: categories
---

<p>
{% for category in site.categories %}
{% capture category_name %}{{ category | first }}{% endcapture %}
<a href = "#{{ category_name }}" class ="tagbox">{{ category_name }}</a>
{% endfor %}
</p>

{% for category in site.categories %}
{% capture category_name %}{{ category | first }}{% endcapture %}
<h3 id="{{ category_name }}">{{ category_name }} </h3>
<p></p>
{% for post in site.categories[category_name] %}
 * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}

{% endfor %}
