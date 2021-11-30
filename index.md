---
layout: base
title: Presentations (@shiltemann)
---

# Welcome!

{{ site.description }}

## Galaxy Workshop setup slides

[bit.ly/galaxy-workshop]({{site.baseurl}}/GalaxyWorkshop/slides.html)


## Presentations

{% for presentation in site.posts  %}
 {% capture current_year %}{{ presentation.date | date: "%Y" }}{% endcapture %}
 {% if current_year != previous_year %}
  {% unless forloop.first %}
    </tbody>
  </table>
  {% endunless %}
  <h2>{{ current_year }}</h2>
  <table class="table table-striped">
   <thead><tr><th>Date</th><th>Title</th><th>Event</th></tr></thead>
   <tbody>
  {% assign previous_year = current_year %}
 {% endif %}
 <tr><td>{{presentation.date| date: "%d-%m-%Y"}}</td><td><a href="{% if presentation.external %}{{presentation.external}}{% else %} {{site.baseurl}}/{{presentation.url}}{% endif %}">{{presentation.title}}</a></td><td>{{presentation.event}}</td></tr>
{% endfor %}
</tbody>
</table>

