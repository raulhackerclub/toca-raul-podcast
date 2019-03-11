---
layout: default
title: Categorias
---

# Categorias

<ul>
{% assign list = site.categories | sort %}
{% for category in list %}
  <li>
    <a href="#{{ category[0] }}">
    {{ category[0] }}
    </a>
    <span>({{ category[1].size }})</span>
  </li>
{% endfor %}
</ul>

{% for category in list %}
  <h2 id="{{ category[0] }}">{{ category[0] }}</h2>
  <ul>
  {% for eps in category[1] %}
    <li>
      <a href="{{ eps.url }}">{{ eps.title }} [{{ eps.date | date: "%d/%m/%Y" }}]</a>
    </li>
  {% endfor %}
  </ul>
{% endfor %}
