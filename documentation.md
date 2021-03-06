---
layout: default
title: Documentation
---

{% for post in site.tags.changelog limit:1 %}

## Documentation

### Guides and reference manual

<a class="download" href="/docs/{{ post.title }}/" title="View documentation">View</a>

GLFW is documented using [Doxygen](http://www.stack.nl/~dimitri/doxygen/), with
both reference documentation and guides both for new users and those who have
used earlier versions.

---
### Example code

This short example shows how the GLFW API looks and how easy it is to create and
a window and OpenGL context with it.  There are many more functions than those
used here, but these are all you need to get started.

{% highlight c %}
#include <GLFW/glfw3.h>

int main(void)
{
    GLFWwindow* window;

    /* Initialize the library */
    if (!glfwInit())
        return -1;

    /* Create a windowed mode window and its OpenGL context */
    window = glfwCreateWindow(640, 480, "Hello World", NULL, NULL);
    if (!window)
    {
        glfwTerminate();
        return -1;
    }

    /* Make the window's context current */
    glfwMakeContextCurrent(window);

    /* Loop until the user closes the window */
    while (!glfwWindowShouldClose(window))
    {
        /* Render here */

        /* Swap front and back buffers */
        glfwSwapBuffers(window);

        /* Poll for and process events */
        glfwPollEvents();
    }

    glfwTerminate();
    return 0;
}
{% endhighlight %}

{% endfor %}
