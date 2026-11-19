---
layout: default
permalink: blog
---

<div style="text-align: center;">
  <img style="margin-top: 20px;" src="images/banner-blog-oscuro.png" alt="Texto alternativo" width="440" height="200">
</div>

<section>
  <h1>Blog</h1>
  <h2>Ensayos, micro-blogs y escritos didácticos</h2>

  <strong>En camino</strong>

  <div style="text-align: center;">
    <a style="margin-bottom: 20px;" class="btn btn-primary" href="{{ '/feed.xml' | relative_url }}"> <i class="fa-solid fa-square-rss"> Feed RSS  </i>  </a>
  </div> 
  
  {% for post in site.posts %}
    {% assign nth = forloop.index0 | modulo:2 %}
    <div class="media t-hackcss-media">

      {% if nth == 0 %}
      <div class="t-hackcss-media-shift media-left">
        <img class="t-hackcss-media-image"
             src="{{ post.image_preview }}" alt="{{ post.title }}"
             title="{{ post.title }}" />
      </div>
      {% endif %}

      <div class="media-body">
        <div class="media-heading">
          <span>{{ post.date | date_to_string }} &raquo;
            {% if post.external_url %}
              <a href="{{ post.external_url }}" target="_blank" title="{{ project.name }}">
                {{ post.title }}
              </a>
            {% else %}
              <a href="{{ post.url | prepend: site.baseurl }}" title="{{ project.name }}">
                {{ post.title }}
              </a>
            {% endif %}
          </span>
        </div>
        <div class="media-content">
          {{ post.short_description }}
        </div>
      </div>

      {% if nth == 1 %}
      <div class="t-hackcss-media-shift media-right">
        <img class="t-hackcss-media-image"
             src="{{ post.image_preview }}" alt="{{ post.title }}"
             title="{{ post.title }}" />
      </div>
      {% endif %}
    </div>
  {% endfor %}
</section>


<script src="https://unpkg.com/vanilla-back-to-top@7.2.1/dist/vanilla-back-to-top.min.js"></script>
<script>addBackToTop({
  diameter: 56,
  backgroundColor: ' #04bcd4 ',
  textColor: ' #d9f6f1 '
})</script>