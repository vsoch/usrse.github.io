---
layout: page
title: RSE Opportunities
permalink: /jobs/
---

## Current RSE openings

<ol>{% for job in site.data.jobs %}
{% capture nowunix %}{{'now' | date: '%s'}}{% endcapture %}
{% capture expires %}{{ job.expires | date: '%s'}}{% endcapture %}
{% capture posted %}{{ job.posted | date: '%b %d, %Y'}}{% endcapture %}

{% if expires > nowunix %}
  {% if posted != '' %}
    <li><a href="{{ job.url }}" target="_blank">{{ job.name }}</a>: {{ job.location }}&emsp;<em>Posted:&nbsp;{{ posted }}</em></li>
  {% else %}
    <li><a href="{{ job.url }}" target="_blank">{{ job.name }}</a>: {{ job.location }}</li>
  {% endif %}
{% endif %}{% endfor %}</ol>

<br>

### Have an RSE-related job posting?  
Contact us via [slack](https://usrse.slack.com) or directly make a pull request in the website's [GitHub repository](https://github.com/USRSE/usrse.github.io).
