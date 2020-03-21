# Flixter - Two-Sided Marketplace #

A two-sided, video-streaming marketplace platform that features credit card payment capabilities, user role management, complex user interfaces, and advanced database relationships. 
<br/>
Tools & Languages: Ruby/Rails, PostgresSQL, Javascript, HTML/CSS

## Table of Contents ##
<ul> 
  <li><a href="#about"> About </a></li>
  <li><a href="#technologies"> Built With </a></li>
  <li><a href="#setup"> Getting Started </a></li>
  <li><a href="#usage"> Deployment </a></li>
  <li><a href="#contact"> Contact</a></li>
</ul>

<div id="about"></div> 

## About ##
This Udemy clone was created as a part of UC Berkeley Extension's Coding Boot Camp Program. 
Like the online learning platform, Udemy, Flixter is an application that allows users to log in as an instructor to host a course, or students to enroll in a course. In the instructor's dashboard, instructors may create and administer courses, determine the enrollment fees, and view the course as a student. Within the course, instructors may add course information, sections, lessons, and upload images and videos. In the student dashboard, students can register and pay for a course or view the courses they are enrolled in. Users may preview courses that are offered by clicking on "learn more". 

<div id="technologies"></div> 

## Built With ##
Flixter integrates the following: 
<ul>
  <li><a href="https://aws.amazon.com/" rel="nofollow">AWS</a></li>
  <li><a href="https://github.com/twbs/bootstrap-rubygem">Bootstrap </a></li>
  <li><a href="https://github.com/carrierwaveuploader/carrierwave">Carrierwave</a></li>
  <li><a href="https://github.com/heartcombo/devise">Devise </a></li>
  <li><a href="https://github.com/plataformatec/simple_form">Simpleform</a></li>
  <li><a href="https://stripe.com/" rel="nofollow">Stripe</a></li>
</ul>

<div id="setup"></div> 

## Getting Started ##
<b> Set Up </b>
In your coding environment, create a new application using PostgreSQL:
  <code> $ rails new flixter --database=postgresql </code>

Once the application is created, enter into your "flixter" text editor and edit your database.yml file accordingly.

Then change directory into your flixter project and create the initial database and start the server
  <code> $ rake db:create</code>

In a separate terminal window, enter into your Flixter folder and set up the web development pipeline
  <code> 
    create new Github repository
    create project in heroku and then deploy it to heroku</code>

<b>Allowing Course Creation</b>
Create a database for course by generating a model for courses 
<code>$ rails generate model course</code>

Then edit the migration file (db/migrate/XXXX_create_courseses.rb) to look like this 
<code>def change
  create_table :courses do |t|
    t.string :title
    t.text :description
    t.decimal :cost
    t.integer :user_id
    t.timestamps
  end
  add_index :courses, :user_id
end</code>

Run the migration in the terminal 
<code> $ rake db:migrate</code>

Then set up the appropriate associations between users and courses.

After, generate a new controller for the instructor dashboard using namespaces.
<code> $ rails generate controller instructor/courses</code>

Connect the controller to the appropriate views and action. 

To ensure user authentication, add a before_action in the controller. (requires the Devise gem)
<code> before_action :authenticate_user!</code>

<div id="usage"></div> 

## Deployment ##
This live project can be view at: https://flixter-robyn-wang.herokuapp.com/

And it's code can be found at: https://github.com/robynwang314/flixter

### Screenshots ###

<b>Landing Page:</b>
<img src="/app/assets/images/home.png" alt="Homepage" width="50%">

<b>Instructors dashboard:</b>
<img src="/app/assets/images/dashboard.png" alt="Instructors Dashboard" width="50%">
<img src="/app/assets/images/contribute.png" alt="Contribute Lesson" width="50%">
<img src="/app/assets/images/administer.png" alt="Administer Lesson" width="50%">

<b>Student View:</b>
<img src="/app/assets/images/lessons.png" alt="Lessons View" width="50%">
<img src="/app/assets/images/course.png" alt="Course View" width="50%">

<div id="contact"></div> 

## Contact ##

<ul>
  <li><a href="http://robynwang-portfolio.herokuapp.com/" target="_blank">Portfolio</a></li>
  <li><a href="https://www.linkedin.com/in/tyrobynwang" target="_blank">LinkedIn</a></li>
  <li><a href="https://github.com/robynwang314" target="_blank">GitHub</a></li>
</ul>