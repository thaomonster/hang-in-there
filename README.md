---
# Hang In There
###### Create Your Own Inspirational Poster!
---
## Table of Contents
[Introduction](#introduction)
[Features](#features)
[Deployment](#deployment)
[Authors](#authors)
[Contributors](#contributors)


## Introduction
The primary goal of [Hang In There](https://github.com/thaomonster/hang-in-there) is to have the user generate random inspirational posters or create their own! This project was created using JS from a blank canvas given only data and one function. ([Project Specs](https://frontend.turing.io/projects/module-1/hang-in-there.html)).

#### Motivation
The motivation behind this projects creation was to build an application to help the user generate their own insiprational poster or if they can't think of anything they can generate a random poster while we focused on writing DRY JS and solidifying good habits in git workflow as a team.

---
## Features
* [Generate Random Poster](#Generate-Random-Poster)
* [Create Custom Poster](#Create-Custom-Poster)
* [Save This Poster](#Save-This-Poster)
* [Show Saved Posters](#Show-Saved-Posters)
* [Double Click to Delete Saved Posters](#Double-Click-to-Delete-Saved-Poster)
* [Continuous Improvement/Future Improvements](#Continuous-Improvement/Future-Improvements)

#### Generate Random Poster
Upon page load, a random poster will be generated, drawing on an array of titles, poster images and quotes 'under the hood'. Clicking on `Show Another Random Poster` in the navigation bar at the bottom of the site will generate a new, random inspirational poster!

<details>
  <summary>**Under the Hood**</summary>
  A database of assetts for the random posters (image titles, and quotes) wwere already provided for the project, which is what is drawn upon to create the poster on page load/refresh. Additional assetts are added dynamically to the respective arrays upon creation of a custom poster - the inputted data is stored away and can now be drawn upon when generating random covers. To creat a random poster, click `Show Another Random Poster` button, an event listener was assigned to the button. Upon click, an assett is chosen at random from each of the arrays for the corresponding poster elements and is placed into a new Class object - the new poster. It is then displayed on the home page by reassigning the corresponding HTML elements, which are targeted with the `document.querySelector()` method.
</details>

#### Create Custom Poster
Click on `Make Your Own Poster` button and fill out the respective inputs, then click the `Show My Poster` button to view the poster.

* **Image** - In this field, enter the url for an image you'd like to use as your poster image.
* **Title** - Enter the desired title for the custom poster. The title will be displayed on the poster.
* **Quote** Enter desired quote for the poster. This quote will be displayed on the poster.

<p align = "center">
<img src="https://media.giphy.com/media/7wzaWSH8oP5ZIR5UUJ/giphy.gif">
</p>
      <details>
        <summary>**Under the Hood**</summary>
        Input fields are cleared when loading the `Make Your Own Poster` section by setting the value of those fields to empty strings. Event listeners are attached to each input field. The value of those input fields, upon click of the `Make Your Own Poster` button, are stored in their respective data arrays (i.e. value of "Images" input will be stored in the "images" data array, within "main.js" file, etc.) with a `.push()` method. Those pieces of information are then drawn on to use in the creation of a new Class object, a new poster, which is then displayed on the main page.
      </details> 

#### Save This Poster
The `Save This Poster` button in the nav bar will save the current random or user generated poster to an array of saved posters. These saved posters can be accessed in the "Show Saved Posters" section at any time.

  <details>
  <summary>**Under the Hood**</summary>
  Using event listeners, corresponding information (values) from the various elements of the currently viewed poster are pulled and then used in the creation of a new Class object (our poster), which is then stored in an array of saved posters (`savedPosters`) to draw upon later (for viewing saved posters). Duplicates within the `savedposters` array are avoided with a separate function. That function compares the key values of the poster being saved against the posters that have been saved in the `savedposters` array - if all of the key values (other than the unique `id`) of the poster being saved match up with any of the object key values in the `savedposters` array, then that is a duplicate poster and it is prevented from being added to the array. 
  </details>

#### Show Saved Posters
Navigate to the "Show Saved Posters" section by clicking the "Show Saved Posters" button in the navigation bar below the poster. This section will display all the posters that were previously saved with the "savedPoster" function (clicking the `Save This Poster` button).

<p align = "center">
<img src="https://media.giphy.com/media/ME6Fvdo8nv9lUo1x9R/giphy.gif">
</p>

  <details>
    <summary>**Under the Hood**</summary>
      To prevent duplicate posters from displaying, we decided to clear HTML elements composing the displayed list of saved posters - which would be leftover from any previous visit to the saved posters section. With the section cleared, a `for loop` is used to iterate through the `savedPosters` array and used in the key values of the poster object at index [i] into the corresponding HTML elements (which are targeted with the `.querySelector()` method). Those elements are then inserted into the HTML using the `insertAdjacentHTML()` method.
  </details>

#### Double Click to Delete Saved Poster
In the "Show Saved Poster" section, double-clicking directly on the saved poster the user wishes to delete will remove that poster from the view and remove it from the array containing the date of that saved poster.

<p align = "center">
<img src="https://media.giphy.com/media/d8Hjqg3VeOpDsch4R2/giphy.gif">
</p>

  <details>
    <summary>**Under the Hood**</summary>
    A new function was declared `deletePoster()` that is responsible for using event delagation, we targeted the class `mini-poster` using the `closest()` method to make sure that if the user double clicks anywhere on the mini poster image it will be deleted. We apply the double click method to an event listener on the window/class of `savedPostersGrid` and when that event listener is triggered it will run the `deletePoster()` function and it will look for matching ID's once it finds a match it will delete the double-clicked element from the savedPosters array and the page.
  </details>

---

## Deployment
# https://thaomonster.github.io/hang-in-there/


#### Continuous Improvement/Future Improvements
 In the next iteration we hope to add:
    * Re-order saved posters
    * Ability to enlarge view of saved cover by clicking on it
    * Error messages if the form is not filled out correctly



## Authors

<table>
    <tr>
        <td> Thao Ma <a href="https://github.com/thaomonster">GH</td>
    </tr>
    </tr>

<td><img src="https://avatars0.githubusercontent.com/u/67611512?s=460&u=539b2ddb5db472ee1db734c0ce522551ad071521&v=4" alt="Ms. Turtle"
 width="150" height="auto" /></td>
</table>


## Contributors
    
    Thank you for your contributions!
        
For his help and direction as a reviewer: <a href="https://github.com/geoff616">Geoff Wright</a>

