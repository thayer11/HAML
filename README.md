What is Haml? 

Haml is a markup language that describes HTML without using inline code. Haml functions as a replacement for inline page templating systems such as PHP, ASP, and ERB. However, Haml avoids the need for explicitly coding HTML into the template, because it itself, is a description of the HTML with some code to generate dynamic content. Haml is to Haiku as Rails is to Omakase. It is simple, clean, and relies on whitespace. 


  Var Haiku = function(Kyle's Voice){
   return ("In the cicada's cry
   There's no sign that can foretell
   How soon it must die.")
  };

  
  Var Omakase = function(Dramatic Reading Mark posted){
    return (" https://www.youtube.com/watch?v=E99FnoYqoII ")
  };

  Var Who is god = function(Holly's twisted mind){
     return (" http://memoryholly.bitballoon.com/ ") 
  };  

Haml is also a pain in the ass because it is VERY opinionated.  

Basic Idea:

HTML/ERB

<section class=”container”>
  <h1><%= post.title %></h1>
  <h2><%= post.subtitle %></h2>
  <div class=”content”>
    <%= post.content %>
  </div>
</section>

HAML

%section.container
  %h1= post.title
  %h2= post.subtitle
  .content
    = post.content
    
  HTML
  
  <strong><%= item.title %></strong>
  
  HAML
  
  %strong= item.title
  
In Haml, we write a tag by using the percent sign and then the name of the tag. This works for %strong, %div, %body, %html, etc. In this cass %section, %h1, %h2, and %div. Then, after the name of the tag is =, which tells Haml to evaluate Ruby code to the right and then print out the return value as the contents of the tag. Unlike the ERB above, Haml will automatically detect newlines in the return value and format the tag properly.

What about adding attributes to tags?

HTML

<strong class="code" id="message">Hello, World!</strong>

Haml

%strong{:class => "code", :id => "message"} Hello, World!

The attributes are just a standard Ruby hash. The class attribute is “code”, the id attribute is “message”. Notice that in this example, we didn’t use =, so “Hello, World!” is interpreted as a normal string, not Ruby code.

There is an easier way to define this tag in Haml, since class and id are such common attributes and since most designers (and developers) are familiar with CSS, we can use similar notation to describe this tag.

%strong.code#message Hello, World!

Why is Haml useful?


Less characters

Less mess---no opening closing divs/inline stuff

Dom is visually represented

Easy to learn


Why shouldn't we use Haml?

Because we are scared of change, devoted to HTML because it's what made us think coding might not be as hard as it is, our parents don't love us, and we are all going to die. 

Oh and it isn't really easy to learn

Additional info: http://haml.info/about.html

The HAML Docs: http://haml.info/docs/yardoc/file.REFERENCE.html#using_haml
