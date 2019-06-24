

```python
%matplotlib inline
```


```python
import numpy as np
import sympy as sp
import matplotlib.pyplot as plt
import math
```

# High-School Maths Exercise
## Getting to Know Jupyter Notebook. Python Libraries and Best Practices. Basic Workflow

# Problem 1. Markdown
Jupyter Notebook is a very light, beautiful and convenient way to organize your research and display your results. Let's play with it for a while.

First, you can double-click each cell and edit its content. If you want to run a cell (that is, execute the code inside it), use Cell > Run Cells in the top menu or press <kbd>Ctrl</kbd> + <kbd>Enter</kbd>.

Second, each cell has a type. There are two main types: Markdown (which is for any kind of free text, explanations, formulas, results... you get the idea), and code (which is, well... for code :D).

Let me give you a...
#### Quick Introduction to Markdown
##### Text and Paragraphs
There are several things that you can do. As you already saw, you can write paragraph text just by typing it. In order to create a new paragraph, just leave a blank line. See how this works below:
```
This is some text.
This text is on a new line, but it will continue the same paragraph (so you can make your paragraphs more easily readable by just continuing on a new line, or just go on and on like this one line is ever continuing).

This text is displayed in a new paragraph.

And this is yet another paragraph.
```
**Result:**

This is some text.
This text is on a new line, but it will continue the same paragraph (so you can make your paragraphs more easily readable by just continuing on a new line, or just go on and on like this one line is ever continuing).

This text is displayed in a new paragraph.

And this is yet another paragraph.

##### Headings
There are six levels of headings. Level one is the highest (largest and most important), and level 6 is the smallest. You can create headings of several types by prefixing the header line with one to six "#" symbols (this is called a pound sign if you are ancient, or a sharp sign if you're a musician... or a hashtag if you're too young :D). Have a look:
```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

**Result:**

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

It is recommended that you have **only one** H1 heading - this should be the header of your notebook (or scientific paper). Below that, you can add your name or just jump to the explanations directly.

##### Emphasis
You can create emphasized (stonger) text by using a **bold** or _italic_ font. You can do this in several ways (using asterisks (\*) or underscores (\_)). In order to "escape" a symbol, prefix it with a backslash (\). You can also strike thorugh your text in order to signify a correction.
```
**bold** __bold__
*italic* _italic_

This is \*\*not \*\* bold.

I ~~didn't make~~ a mistake.
```

**Result:**

**bold** __bold__
*italic* _italic_

This is \*\*not\*\* bold.

I ~~didn't make~~ a mistake.

##### Lists
You can add two types of lists: ordered and unordered. Lists can also be nested inside one another. To do this, press <kbd>Tab</kbd> once (it will be converted to 4 spaces).

To create an ordered list, just type the numbers. Don't worry if your numbers are wrong - Jupyter Notebook will create them properly for you. Well, it's better to have them properly numbered anyway...
```
1. This is
2. A list
10. With many
9. Items
    1. Some of which
    2. Can
        3. Be nested
42. You can also
    * Mix 
    * list
    * types
```

**Result:**
1. This is
2. A list
10. With many
9. Items
    1. Some of which
    2. Can
        3. Be nested
42. You can also
    * Mix 
    * list
    * types
    
To create an unordered list, type an asterisk, plus or minus at the beginning:
```
* This is
* An
    + Unordered
    - list
```

**Result:**
* This is
* An
    + Unordered
        - list
        
##### Links
There are many ways to create links but we mostly use one of them: we present links with some explanatory text. See how it works:
```
This is [a link](http://google.com) to Google.
```

**Result:**

This is [a link](http://google.com) to Google.

##### Images
They are very similar to links. Just prefix the image with an exclamation mark. The alt(ernative) text will be displayed if the image is not available. Have a look (hover over the image to see the title text):
```
![Alt text](http://i.imgur.com/dkY1gph.jpg "Do you know that "taco cat" is a palindrome? Thanks to The Oatmeal :)")
```

**Result:**

![Alt text](http://i.imgur.com/dkY1gph.jpg "Do you know that "taco cat" is a palindrome? Thanks to The Oatmeal :)")

If you want to resize images or do some more advanced stuff, just use HTML. 

Did I mention these cells support HTML, CSS and JavaScript? Now I did.

##### Tables
These are a pain because they need to be formatted (somewhat) properly. Here's a good [table generator](http://www.tablesgenerator.com/markdown_tables). Just select File > Paste table data... and provide a tab-separated list of values. It will generate a good-looking ASCII-art table for you.
```
| Cell1 | Cell2 | Cell3 |
|-------|-------|-------|
| 1.1   | 1.2   | 1.3   |
| 2.1   | 2.2   | 2.3   |
| 3.1   | 3.2   | 3.3   |
```

**Result:**

| Cell1 | Cell2 | Cell3 |
|-------|-------|-------|
| 1.1   | 1.2   | 1.3   |
| 2.1   | 2.2   | 2.3   |
| 3.1   | 3.2   | 3.3   |

##### Code
Just use triple backtick symbols. If you provide a language, it will be syntax-highlighted. You can also use inline code with single backticks.
<pre>
```python
def square(x):
    return x ** 2
```
This is `inline` code. No syntax highlighting here.
</pre>

**Result:**
```python
def square(x):
    return x ** 2
```
This is `inline` code. No syntax highlighting here.

**Now it's your turn to have some Markdown fun.** In the next cell, try out some of the commands. You can just throw in some things, or do something more structured (like a small notebook).

# Main Title
## Heading 2

Lorem ipsum dolor sit amet

1. Content
    * random stuff
    * random stuff 2
2. Resources
    + math resources
    - programming resources
    
This link is to [StackOverflow](https://stackoverflow.com/)

Some image:
![alternative text](http://i.imgur.com/dkY1gph.jpg "Alternative" )

Some table:

| ID | Name   | Age |
|----|--------|-----|
| 1  | John   | 23  |
| 2  | Lindsy | 22  |
| 3  | Gareth | 24  |


### Problem 2. Formulas and LaTeX
Writing math formulas has always been hard. But scientists don't like difficulties and prefer standards. So, thanks to Donald Knuth (a very popular computer scientist, who also invented a lot of algorithms), we have a nice typesetting system, called LaTeX (pronounced _lah_-tek). We'll be using it mostly for math formulas, but it has a lot of other things to offer.

There are two main ways to write formulas. You could enclose them in single `$` signs like this: `$ ax + b $`, which will create an **inline formula**: $ ax + b $. You can also enclose them in double `$` signs `$$ ax + b $$` to produce $$ ax + b $$.

Most commands start with a backslash and accept parameters either in square brackets `[]` or in curly braces `{}`. For example, to make a fraction, you typically would write `$$ \frac{a}{b} $$`: $$ \frac{a}{b} $$.

[Here's a resource](http://www.stat.pitt.edu/stoffer/freetex/latex%20basics.pdf) where you can look up the basics of the math syntax. You can also search StackOverflow - there are all sorts of solutions there.

You're on your own now. Research and recreate all formulas shown in the next cell. Try to make your cell look exactly the same as mine. It's an image, so don't try to cheat by copy/pasting :D.

Note that you **do not** need to understand the formulas, what's written there or what it means. We'll have fun with these later in the course.

![Math formulas and equations](math.jpg)

Equation of a line: 
$$ y = ax + b $$
Roots of the quadratic equation: $ ax^2 + bx + c = 0 $
$$ x_{1,2}=\frac{ - b \pm \sqrt {b^2 - 4ac}}{2a} $$
Taylor series expansion:
$$ \left.f(x)\right|_{x=a} = f(a) + f^{'}(a)(x-a) + \frac{f^n(a)}{2!}(x-a)^2 + \cdots + \frac{f^{(n)}(a)}{n!}(x-a)^n + \cdots$$
Binomial thoerem:
$$ (x+y)^n = \left( \begin{array}{c} n \\ 0 \end{array}  \right)x^ny^0 + \left( \begin{array}{c} n \\ 1 \end{array} \right) x^1y^{n-1} + \cdots + \left( \begin{array}{c} n \\ n \end{array} \right)x^0y^n = \sum^n_{k=0} \left( \begin{array}{c} n \\ k \end{array} \right)x^{n-k}y^k$$
An integral (this one is lot of fun to solve :D):
$$ \int^{+\infty}_{-\infty} e^{-x^2}dx = \sqrt\pi $$
A short matrix:
$$ \left( \begin{array}{c} 2\\2\\6 \end{array} \textrm{ } \begin{array}{c} 1\\6\\8 \end{array} \textrm{ } \begin{array}{c} 3\\8\\18 \end{array} \right) $$
A long matrix:
$$ A = \left( \begin{array}{c} a_{11} \\ a_{21} \\ \vdots \\ a_{m1} \end{array} \textrm{ } \begin{array}{c} a_{12} \\ a_{22} \\ \vdots \\ a_{m2} \end{array} \textrm{ } \begin{array}{c} \cdots \\ \cdots \\ \ddots \\ \cdots \end{array} \textrm{ } \begin{array}{c} a_{1n} \\ a_{2n} \\ \vdots \\ a_{mn} \end{array} \textrm{ } \right) $$

### Problem 3. Solving with Python
Let's first do some symbolic computation. We need to import `sympy` first. 

**Should your imports be in a single cell at the top or should they appear as they are used?** There's not a single valid best practice. Most people seem to prefer imports at the top of the file though. **Note: If you write new code in a cell, you have to re-execute it!**

Let's use `sympy` to give us a quick symbolic solution to our equation. First import `sympy` (you can use the second cell in this notebook): 
```python 
import sympy 
```

Next, create symbols for all variables and parameters. You may prefer to do this in one pass or separately:
```python 
x = sympy.symbols('x')
a, b, c = sympy.symbols('a b c')
```

Now solve:
```python 
sympy.solve(a * x**2 + b * x + c)
```

Hmmmm... we didn't expect that :(. We got an expression for $a$ because the library tried to solve for the first symbol it saw. This is an equation and we have to solve for $x$. We can provide it as a second paramter:
```python 
sympy.solve(a * x**2 + b * x + c, x)
```

Finally, if we use `sympy.init_printing()`, we'll get a LaTeX-formatted result instead of a typed one. This is very useful because it produces better-looking formulas.


```python
sp.init_printing()
x,a,b,c = sp.symbols('x a b c')
sp.solve(a * x**2 + b * x + c, x)

```




$$\left [ \frac{1}{2 a} \left(- b + \sqrt{- 4 a c + b^{2}}\right), \quad - \frac{1}{2 a} \left(b + \sqrt{- 4 a c + b^{2}}\right)\right ]$$



How about a function that takes $a, b, c$ (assume they are real numbers, you don't need to do additional checks on them) and returns the **real** roots of the quadratic equation?

Remember that in order to calculate the roots, we first need to see whether the expression under the square root sign is non-negative.

If $b^2 - 4ac > 0$, the equation has two real roots: $x_1, x_2$

If $b^2 - 4ac = 0$, the equation has one real root: $x_1 = x_2$

If $b^2 - 4ac < 0$, the equation has zero real roots

Write a function which returns the roots. In the first case, return a list of 2 numbers: `[2, 3]`. In the second case, return a list of only one number: `[2]`. In the third case, return an empty list: `[]`.


```python
import math
def solve_quadratic_equation(a, b, c):
    """
    Returns the real solutions of the quadratic equation ax^2 + bx + c = 0
    """
    # Delete the "pass" statement below and write your code
    D = b**2 - 4*a*c
    if D < 0:
        return []
    elif D == 0:
        x = -b / 2*a
        return [x]
    else:
        x1 = (-b - math.sqrt(D)) / (2*a)
        x2 = (-b + math.sqrt(D)) / (2*a)
        return [x1,x2]
```


```python
# Testing: Execute this cell. The outputs should match the expected outputs. Feel free to write more tests
print(solve_quadratic_equation(1, -1, -2)) # [-1.0, 2.0]
print(solve_quadratic_equation(1, -8, 16)) # [4.0]
print(solve_quadratic_equation(41, -8, 25)) # []
print(solve_quadratic_equation(21, -8, 25)) # []
```

    [-1.0, 2.0]
    [4.0]
    []
    []


**Bonus:** Last time we saw how to solve a linear equation. Remember that linear equations are just like quadratic equations with $a = 0$. In this case, however, division by 0 will throw an error. Extend your function above to support solving linear equations (in the same way we did it last time).


```python

def solve_quadratic_equation(a, b, c):
    """
    Returns the real solutions of the quadratic equation ax^2 + bx + c = 0 and if a = 0 it returns the real solutions of
    the linear equation bx + c = 0
    """
    # Delete the "pass" statement below and write your code
    if a != 0:
        D = b**2 - 4*a*c
        if D < 0:
            return []
        elif D == 0:
            x = -b / 2*a
            return [x]
        else:
            x1 = (-b - math.sqrt(D)) / (2*a)
            x2 = (-b + math.sqrt(D)) / (2*a)
            return [x1,x2]
    else:
        if b == 0:
            if c == 0:
                return []
            else:
                return math.nan
        else:
            return -c / b
```


```python
print(solve_quadratic_equation(0,1,1))
print(solve_quadratic_equation(0,0,2))
print(solve_quadratic_equation(0,2,0))
print(solve_quadratic_equation(0,0,0))
```

    -1.0
    nan
    0.0
    []


### Problem 4. Equation of a Line
Let's go back to our linear equations and systems. There are many ways to define what "linear" means, but they all boil down to the same thing.

The equation $ax + b = 0$ is called *linear* because the function $f(x) = ax+b$ is a linear function. We know that there are several ways to know what one particular function means. One of them is to just write the expression for it, as we did above. Another way is to **plot** it. This is one of the most exciting parts of maths and science - when we have to fiddle around with beautiful plots (although not so beautiful in this case).

The function produces a straight line and we can see it.

How do we plot functions in general? Ww know that functions take many (possibly infinitely many) inputs. We can't draw all of them. We could, however, evaluate the function at some points and connect them with tiny straight lines. If the points are too many, we won't notice - the plot will look smooth.

Now, let's take a function, e.g. $y = 2x + 3$ and plot it. For this, we're going to use `numpy` arrays. This is a special type of array which has two characteristics:
* All elements in it must be of the same type
* All operations are **broadcast**: if `x = [1, 2, 3, 10]` and we write `2 * x`, we'll get `[2, 4, 6, 20]`. That is, all operations are performed at all indices. This is very powerful, easy to use and saves us A LOT of looping.

There's one more thing: it's blazingly fast because all computations are done in C, instead of Python.

First let's import `numpy`. Since the name is a bit long, a common convention is to give it an **alias**:
```python
import numpy as np
```

Import that at the top cell and don't forget to re-run it.

Next, let's create a range of values, e.g. $[-3, 5]$. There are two ways to do this. `np.arange(start, stop, step)` will give us evenly spaced numbers with a given step, while `np.linspace(start, stop, num)` will give us `num` samples. You see, one uses a fixed step, the other uses a number of points to return. When plotting functions, we usually use the latter. Let's generate, say, 1000 points (we know a straight line only needs two but we're generalizing the concept of plotting here :)).
```python
x = np.linspace(-3, 5, 1000)
```
Now, let's generate our function variable
```python
y = 2 * x + 3
```

We can print the values if we like but we're more interested in plotting them. To do this, first let's import a plotting library. `matplotlib` is the most commnly used one and we usually give it an alias as well.
```python
import matplotlib.pyplot as plt
```

Now, let's plot the values. To do this, we just call the `plot()` function. Notice that the top-most part of this notebook contains a "magic string": `%matplotlib inline`. This hints Jupyter to display all plots inside the notebook. However, it's a good practice to call `show()` after our plot is ready.
```python
plt.plot(x, y)
plt.show()
```


```python
plt.show()
x = np.linspace(-3,5,1000)
y = 2 * x + 3
plt.plot(x, y)
```




    [<matplotlib.lines.Line2D at 0x11f0120f0>]




![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_17_1.png)


It doesn't look too bad bit we can do much better. See how the axes don't look like they should? Let's move them to zeto. This can be done using the "spines" of the plot (i.e. the borders).

All `matplotlib` figures can have many plots (subfigures) inside them. That's why when performing an operation, we have to specify a target figure. There is a default one and we can get it by using `plt.gca()`. We usually call it `ax` for "axis".
Let's save it in a variable (in order to prevent multiple calculations and to make code prettier). Let's now move the bottom and left spines to the origin $(0, 0)$ and hide the top and right one.
```python
ax = plt.gca()
ax.spines["bottom"].set_position("zero")
ax.spines["left"].set_position("zero")
ax.spines["top"].set_visible(False)
ax.spines["right"].set_visible(False)
```

**Note:** All plot manipulations HAVE TO be done before calling `show()`. It's up to you whether they should be before or after the function you're plotting.

This should look better now. We can, of course, do much better (e.g. remove the double 0 at the origin and replace it with a single one), but this is left as an exercise for the reader :).


```python
plt.show()
x = np.linspace(-3,5,1000)
y = 2 * x + 3
plt.plot(x, y)
ax = plt.gca()
ax.set_ylim(0.1,13)#hiding the 0 on the y (setting a limit)
ax.spines["bottom"].set_position("zero")
ax.spines["left"].set_position("zero")
ax.spines["top"].set_visible(False)
ax.spines["right"].set_visible(False)


```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_19_0.png)


### * Problem 5. Linearizing Functions
Why is the line equation so useful? The main reason is because it's so easy to work with. Scientists actually try their best to linearize functions, that is, to make linear functions from non-linear ones. There are several ways of doing this. One of them involves derivatives and we'll talk about it later in the course. 

A commonly used method for linearizing functions is through algebraic transformations. Try to linearize 
$$ y = ae^{bx} $$

Hint: The inverse operation of $e^{x}$ is $\ln(x)$. Start by taking $\ln$ of both sides and see what you can do. Your goal is to transform the function into another, linear function. You can look up more hints on the Internet :).

$$\ln(y) = \ln(ae^{bx})$$
$$\downdownarrows$$
$$ \ln(y) = \ln(a) + \ln(e^{bx}) $$
$$\downdownarrows$$
$$ \ln(y) = \ln(a) + bx $$
If we say that $ z = \ln(y) $ :
$$ z = \ln(a) + bx $$

### * Problem 6. Generalizing the Plotting Function
Let's now use the power of Python to generalize the code we created to plot. In Python, you can pass functions as parameters to other functions. We'll utilize this to pass the math function that we're going to plot.

Note: We can also pass *lambda expressions* (anonymous functions) like this: 
```python
lambda x: x + 2```
This is a shorter way to write
```python
def some_anonymous_function(x):
    return x + 2
```

We'll also need a range of x values. We may also provide other optional parameters which will help set up our plot. These may include titles, legends, colors, fonts, etc. Let's stick to the basics now.

Write a Python function which takes another function, x range and number of points, and plots the function graph by evaluating it at every point.

**BIG hint:** If you want to use not only `numpy` functions for `f` but any one function, a very useful (and easy) thing to do, is to vectorize the function `f` (e.g. to allow it to be used with `numpy` broadcasting):
```python
f_vectorized = np.vectorize(f)
y = f_vectorized(x)
```


```python
def plot_math_function(f, min_x, max_x, num_points):
    # Write your code here
    x = np.linspace(min_x,max_x,num_points)
    f_vectorized = np.vectorize(f)
    y = f_vectorized(x)
    
    plt.plot(x,y)
    plt.show()
    ax = plt.gca()
    ax.spines["bottom"].set_position("zero")
    ax.spines["left"].set_position("zero")
    ax.spines["top"].set_visible(False)
    ax.spines["right"].set_visible(False)
    
```


```python
plot_math_function(lambda x: 2 * x + 3, -3, 5, 1000)
plot_math_function(lambda x: -x + 8, -1, 10, 1000)
plot_math_function(lambda x: x**2 - x - 2, -3, 4, 1000)
plot_math_function(lambda x: np.sin(x), -np.pi, np.pi, 1000)
plot_math_function(lambda x: np.sin(x) / x, -4 * np.pi, 4 * np.pi, 1000)
```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_0.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_1.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_2.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_3.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_4.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_24_5.png)


### * Problem 7. Solving Equations Graphically
Now that we have a general plotting function, we can use it for more interesting things. Sometimes we don't need to know what the exact solution is, just to see where it lies. We can do this by plotting the two functions around the "=" sign ans seeing where they intersect. Take, for example, the equation $2x + 3 = 0$. The two functions are $f(x) = 2x + 3$ and $g(x) = 0$. Since they should be equal, the point of their intersection is the solution of the given equation. We don't need to bother marking the point of intersection right now, just showing the functions.

To do this, we'll need to improve our plotting function yet once. This time we'll need to take multiple functions and plot them all on the same graph. Note that we still need to provide the $[x_{min}; x_{max}]$ range and it's going to be the same for all functions.

```python
vectorized_fs = [np.vectorize(f) for f in functions]
ys = [vectorized_f(x) for vectorized_f in vectorized_fs]
```


```python
def plot_math_functions(functions, min_x, max_x, num_points):
    # Write your code here
    x = np.linspace(min_x,max_x,num_points)
    vectorized_fs = [np.vectorize(f) for f in functions]
    ys = [vectorized_f(x) for vectorized_f in vectorized_fs]
    for y in ys:
        plt.plot(x,y)
    ax = plt.gca()
    ax.spines["bottom"].set_position("zero")
    ax.spines["left"].set_position("zero")
    ax.spines["top"].set_visible(False)
    ax.spines["right"].set_visible(False)
    plt.show()
```


```python
plot_math_functions([lambda x: 2 * x + 3, lambda x: 0],-3,5,1000)
plot_math_functions([lambda x: 3 * x**2 - 2 * x + 5, lambda x: 3 * x + 7], -2, 3, 1000)
```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_27_0.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_27_1.png)


This is also a way to plot the solutions of systems of equation, like the one we solved last time. Let's actually try it.


```python
plot_math_functions([lambda x: (-4 * x + 7) / 3, lambda x: (-3 * x + 8) / 5, lambda x: (-x - 1) / -2], -1, 4, 1000)
```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_29_0.png)


### Problem 8. Trigonometric Functions
We already saw the graph of the function $y = \sin(x)$. But, how do we define the trigonometric functions once again? Let's quickly review that.

<img src="angle-in-right-triangle.png" style="max-height: 200px" alt="Right triangle" />

The two basic trigonometric functions are defined as the ratio of two sides:
$$ \sin(x) = \frac{\text{opposite}}{\text{hypotenuse}} $$
$$ \cos(x) = \frac{\text{adjacent}}{\text{hypotenuse}} $$

And also:
$$ \tan(x) = \frac{\text{opposite}}{\text{adjacent}} = \frac{\sin(x)}{\cos(x)} $$
$$ \cot(x) = \frac{\text{adjacent}}{\text{opposite}} = \frac{\cos(x)}{\sin(x)} $$

This is fine, but using this, "right-triangle" definition, we're able to calculate the trigonometric functions of angles up to $90^\circ$. But we can do better. Let's now imagine a circle centered at the origin of the coordinate system, with radius $r = 1$. This is called a "unit circle".

<img src="triangle-unit-circle.png" style="max-height: 300px" alt="Trigonometric unit circle" />

We can now see exactly the same picture. The $x$-coordinate of the point in the circle corresponds to $\cos(\alpha)$ and the $y$-coordinate - to $\sin(\alpha)$. What did we get? We're now able to define the trigonometric functions for all degrees up to $360^\circ$. After that, the same values repeat: these functions are **periodic**: 
$$ \sin(k.360^\circ + \alpha) = \sin(\alpha), k = 0, 1, 2, \dots $$
$$ \cos(k.360^\circ + \alpha) = \cos(\alpha), k = 0, 1, 2, \dots $$

We can, of course, use this picture to derive other identities, such as:
$$ \sin(90^\circ + \alpha) = \cos(\alpha) $$

A very important property of the sine and cosine is that they accept values in the range $(-\infty; \infty)$ and produce values in the range $[-1; 1]$. The two other functions take values in the range $(-\infty; \infty)$ **except when their denominators are zero** and produce values in the same range. 

#### Radians
A degree is a geometric object, $1/360$th of a full circle. This is quite inconvenient when we work with angles. There is another, natural and intrinsic measure of angles. It's called the **radian** and can be written as $\text{rad}$ or without any designation, so $\sin(2)$ means "sine of two radians".
![Radian definition](radian.gif)

It's defined as *the central angle of an arc with length equal to the circle's radius* and $1\text{rad} \approx 57.296^\circ$.

We know that the circle circumference is $C = 2\pi r$, therefore we can fit exactly $2\pi$ arcs with length $r$ in $C$. The angle corresponding to this is $360^\circ$ or $2\pi\ \text{rad}$. Also, $\pi rad = 180^\circ$.

(Some people prefer using $\tau = 2\pi$ to avoid confusion with always multiplying by 2 or 0.5 but we'll use the standard notation here.)

**NOTE:** All trigonometric functions in `math` and `numpy` accept radians as arguments. In order to convert between radians and degrees, you can use the relations $\text{[deg]} = 180/\pi.\text{[rad]}, \text{[rad]} =  \pi/180.\text{[deg]}$. This can be done using `np.deg2rad()` and `np.rad2deg()` respectively.

#### Inverse trigonometric functions
All trigonometric functions have their inverses. If you plug in, say $\pi/4$ in the $\sin(x)$ function, you get $\sqrt{2}/2$. The inverse functions (also called, arc-functions) take arguments in the interval $[-1; 1]$ and return the angle that they correspond to. Take arcsine for example:
$$ \arcsin(y) = x: sin(y) = x $$
$$ \arcsin\left(\frac{\sqrt{2}}{2}\right) = \frac{\pi}{4} $$

Please note that this is NOT entirely correct. From the relations we found:
$$\sin(x) = sin(2k\pi + x), k = 0, 1, 2, \dots $$

it follows that $\arcsin(x)$ has infinitely many values, separated by $2k\pi$ radians each:
$$ \arcsin\left(\frac{\sqrt{2}}{2}\right) = \frac{\pi}{4} + 2k\pi, k = 0, 1, 2, \dots $$

In most cases, however, we're interested in the first value (when $k = 0$). It's called the **principal value**.

Note 1: There are inverse functions for all four basic trigonometric functions: $\arcsin$, $\arccos$, $\arctan$, $\text{arccot}$. These are sometimes written as $\sin^{-1}(x)$, $cos^{-1}(x)$, etc. These definitions are completely equivalent. 

Just notice the difference between $\sin^{-1}(x) := \arcsin(x)$ and $\sin(x^{-1}) = \sin(1/x)$.

#### Exercise
Use the plotting function you wrote above to plot the inverse trigonometric functions.


```python
plot_math_functions([lambda x: math.asin(x)],-1,1,1000)
plot_math_functions([lambda x: math.acos(x)],-1,1,1000)
plot_math_functions([lambda x: math.atan(x)],-1,1,1000)
plot_math_functions([lambda x: sp.acot(x)],-1,1,1000)
plot_math_functions([lambda x: math.asin(x), lambda x: math.acos(x), lambda x: math.atan(x),lambda x: math.atan(1/x)], -1, 1, 1000)
```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_32_0.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_32_1.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_32_2.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_32_3.png)



![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_32_4.png)



```python
def plot_circle(x_c, y_c, r):
    """
    Plots the circle with center C(x_c; y_c) and radius r.
    This corresponds to plotting the equation x^2 + y^2 = r^2
    """
    # Write your code here
    phi = np.linspace(0, 2 * np.pi,1000)
    x = r * np.cos(phi)
    y = r * np.sin(phi)
    plt.gca().set_aspect("equal")
    plt.plot(x,y)
    plt.show()

```


```python
plot_circle(3,6,4)
```


![png](High-School%20Maths%20Exercise_files/High-School%20Maths%20Exercise_34_0.png)


### ** Problem 9. Perlin Noise
This algorithm has many applications in computer graphics and can serve to demonstrate several things... and help us learn about math, algorithms and Python :).
#### Noise
Noise is just random values. We can generate noise by just calling a random generator. Note that these are actually called *pseudorandom generators*. We'll talk about this later in this course.
We can generate noise in however many dimensions we want. For example, if we want to generate a single dimension, we just pick N random values and call it a day. If we want to generate a 2D noise space, we can take an approach which is similar to what we already did with `np.meshgrid()`.

$$ \text{noise}(x, y) = N, N \in [n_{min}, n_{max}] $$

This function takes two coordinates and returns a single number N between $n_{min}$ and $n_{max}$. (This is what we call a "scalar field").

Random variables are always connected to **distributions**. We'll talk about these a great deal but now let's just say that these define what our noise will look like. In the most basic case, we can have "uniform noise" - that is, each point in our little noise space $[n_{min}, n_{max}]$ will have an equal chance (probability) of being selected.

#### Perlin noise
There are many more distributions but right now we'll want to have a look at a particular one. **Perlin noise** is a kind of noise which looks smooth. It looks cool, especially if it's colored. The output may be tweaked to look like clouds, fire, etc. 3D Perlin noise is most widely used to generate random terrain.

#### Algorithm
... Now you're on your own :). Research how the algorithm is implemented (note that this will require that you understand some other basic concepts like vectors and gradients).

#### Your task
1. Research about the problem. See what articles, papers, Python notebooks, demos, etc. other people have created
2. Create a new notebook and document your findings. Include any assumptions, models, formulas, etc. that you're using
3. Implement the algorithm. Try not to copy others' work, rather try to do it on your own using the model you've created
4. Test and improve the algorithm
5. (Optional) Create a cool demo :), e.g. using Perlin noise to simulate clouds. You can even do an animation (hint: you'll need gradients not only in space but also in time)
6. Communicate the results (e.g. in the Softuni forum)

Hint: [This](http://flafla2.github.io/2014/08/09/perlinnoise.html) is a very good resource. It can show you both how to organize your notebook (which is important) and how to implement the algorithm.
