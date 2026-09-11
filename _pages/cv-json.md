---
layout: archive
title: "CV"
permalink: /cv-json/
author_profile: true
redirect_from:
  - /resume-json
---

{% include base_path %}
{% assign cv = site.data.cv %}
{% assign cv_pdf = cv.basics.pdf | default: "/files/cv.pdf" %}
{% if cv_pdf contains "://" %}
  {% assign cv_pdf_url = cv_pdf %}
{% else %}
  {% assign cv_pdf_url = cv_pdf | prepend: base_path %}
{% endif %}

<div class="cv-download-links">
  <a href="{{ cv_pdf_url }}" class="btn btn--primary" target="_blank" rel="noopener">Download CV as PDF</a>
</div>

<div class="cv-pdf-viewer">
  <iframe
    src="{{ cv_pdf_url }}#view=FitH"
    title="{{ cv.basics.name | default: site.name }} CV"
    loading="lazy">
  </iframe>
  <p class="cv-pdf-fallback">
    Unable to display the PDF inline.
    <a href="{{ cv_pdf_url }}" target="_blank" rel="noopener">Open or download the CV</a>.
  </p>
</div>
