Untitled Pages Theme
====================

This is a Jekyll theme that I'm working on for my personal website.  It is
designed with simplicity and ease of modification in mind, with fairly
minimal styling and minimal JavaScript.  This is well-suited to people like me
who are fairly comfortable with programming and writing but don't have much of
an eye for web design; indeed the website was made specifically to look like a
programmer's website.

You can see a live preview of Untitled Pages Theme [here][preview]

[preview]: https://pages-theme.pavlick.net/

Setup
-----

Untitled Pages Theme should work right out of the box on any Jekyll website;
simply copy all of the files in the repository into your site and replace
`index.md` with your own index page.  Templates for blog posts are ready to
go.

To edit the navbar on top, edit `_data/navigation.yml` with any pages that you
want to see up there.  The buttons on the navbar will resize so that they
all fit.

See the [Jekyll Step-by-Step Guide][Jekyll Guide] for more info on how to set
up your own website using Jekyll.

[Jekyll Guide]: https://jekyllrb.com/docs/step-by-step/01-setup/

Features
--------

One of the unique features of Untitled Pages Theme, and something I think is
criminally underrepresented in GitHub Pages sites, is predefined classes for
images to float to the left or right of the text.  For example, an image in
the `float-left` class will appear to the left of the text and the text will
wrap around it like an illustration in a book.

Floating images can also be used as preview images for blog posts, which can
be featured on the blog index page.  To implement this feature, you may put
something like this in your `blog.html` file:

```html
{% for post in site.posts %}
    {% assign even = forloop.index0 | modulo: 2 %}

    <p>
        <strong><a href = "{{ post.url }}"><{{ post.title }}></a></strong>
    </p>

    {{ post.excerpt }}

    {% if post.image %}

        {% if even == 0 %}
            <img src = "{{ post.image }}" class = "float-left" />
        {% else %}
            <img src = "{{ post.image }}" class = "float-right" />
        {% endif %}

    {% endif %}

{% endfor %}
```

In this example, the preview images will, if present, alternate between the
left and right sides of the post excerpt.

License
-------

Untitled Pages Theme is [in the public domain][CC0].  I made it with the goal
of enabling other people to use my website layout for free with no intention
of claiming any exclusive rights to it.  If you want to give me ~~blame~~
credit for the layout that's not necessary, though I would highly appreciate
it :-)

See [LICENSE][CC0] for details about the public domain dedication.

[CC0]: LICENSE
