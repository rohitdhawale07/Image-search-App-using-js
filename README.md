# Image-search-App-using-js
## Hosted Link :- https://rohitdhawale07.github.io/Image-search-App-using-js/
Creating a complete image search app using JavaScript involves several components, including HTML 
for the user interface, CSS for styling, JavaScript for functionality, and 
a back-end service or API for retrieving image search results. 
In this example, I'll guide you through creating a simple image search app using the Unsplash API.

Here's a step-by-step guide, including the full code and explanations:

1. Set up your project structure:

Create a folder for your project and add three files: index.html, styles.css, and script.js.

2. HTML (index.html):
## HTML code
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image search App</title>
    <link rel="stylesheet" href="./style.css">
</head>
<body>
    <h1>Image Search App</h1>
    <form action="">
        <input type="text" placeholder="Search for images..." name="" id="search-input">
        <button id="search-button" >Search</button>
    </form>
    <div id="search-results">
        <!-- <div class="search-result">
            <img src="https://images.unsplash.com/photo-1693922874336-fd3c4b0084b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Khana Khajana">
            <a href="https://unsplash.com/photos/a-wooden-table-topped-with-plates-of-food-7y2vVGzAQ2o" target="_blank">Khana khajana</a>
        </div>
        <div class="search-result">
            <img src="https://images.unsplash.com/photo-1693922874336-fd3c4b0084b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Khana Khajana">
            <a href="https://unsplash.com/photos/a-wooden-table-topped-with-plates-of-food-7y2vVGzAQ2o" target="_blank">Khana khajana</a>
        </div>
        <div class="search-result">
            <img src="https://images.unsplash.com/photo-1693922874336-fd3c4b0084b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1480&q=80" alt="Khana Khajana">
            <a href="https://unsplash.com/photos/a-wooden-table-topped-with-plates-of-food-7y2vVGzAQ2o" target="_blank">Khana khajana</a>
        </div> -->
    </div>
    <button id="show-more-button">Show More</button>

    <script src="./index.js"></script>
</body>
</html>
```
This HTML code sets up the basic structure of the app, including the search input field and a container for displaying the search results.

3. CSS (styles.css):
   ## CSS Code :-
```
   *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: cursive;
    background-color: rgb(244, 249, 253);
}
body{
    width: 100%;
    height: 100vh;
}
h1{
    text-align: center;
    margin-top: 2rem;
    color: rgb(58, 58, 58);
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    font-size: 2.6rem;

}
form{
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 2rem;
    margin-bottom: 2rem;

}
form #search-input {
    margin-right: .5rem;
    padding: 6px 10px;
    font-size: 1.1rem;
    background-color: white;
    border: none;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px, rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
}
#search-button{
    padding: 4px 10px;
    background-color: royalblue;
    color: white;
    font-size: 1.3rem;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
#search-button:hover{
    color: black;
    background-color: rgb(184, 184, 9);
    scale: 1.02;
}
#show-more-button{
        background-color: royalblue;
        border: none;
        color: white;
        padding: 6px 20px;
        display: block;
        margin: 20px auto;
        text-align: center;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease-in-out;
        display: none;
    }
#search-results{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    max-width: 1200px;
    margin: 0 auto;

}
.search-result{
    margin-bottom: 3rem;
    width: 30%;
    height: 100%;
    border-radius: 5px;
    box-shadow: 0 0 6px rgba(0,0,0,0.2);
    overflow: hidden;

}
.search-result img{
    width: 100%;
    height: 300px;
    object-fit: cover;
    transition: opacity 0.2s ease-in-out;
}
.search-result:hover{
    opacity: 0.7;
}
.search-result a{
    font-size: 1.2rem;
    text-decoration: none;
    color: #333;
    display: block;
    padding: 10px;
    text-transform: capitalize;
}

@media screen and (max-width:768px) {
    #search-results {
        padding: 20px;
    }
    .search-result{
        width:45%;
    }
}
@media screen and (max-width:480px) {
    .search-result{
        width:100%;
    }
}

```

In this JavaScript code:

We select the necessary DOM elements and add an event listener to the search button.
When the user clicks the button, we validate the input, construct the Unsplash API URL with your API key, and fetch the data.
We then display the retrieved images by creating HTML elements and appending them to the imageContainer.
5. Get an API Key:

To make this code work, you need to sign up for the Unsplash API and replace 'YOUR_UNSPLASH_API_KEY' in the JavaScript code with your actual API key.

6. Run the App:

Open index.html in a web browser, and you should have a functioning image search app.

Remember that this is a basic example.
In a production application, you would want to handle error states, pagination, and other features depending on your requirements.
 Additionally, please be aware of any API usage limits or terms of service when using external APIs like Unsplash

## JAVASCRIPT code
```
const accessKey = "DemGIicSYKgvy9mbsRD7q-_oF6CuZpAhD8NHWXRTy04";

const form = document.querySelector("form");
const searchInput = document.getElementById("search-input");
const searchResults = document.querySelector("#search-results");
const showMoreButton = document.getElementById("show-more-button");


let inputData = "";
let page = 1;

async function searchImages() {
  inputData = searchInput.value;
  const url = `https://api.unsplash.com/search/photos?page=${page}&query=${inputData}&client_id=${accessKey}`;

  const response = await fetch(url);
  const data = await response.json();
  if (page === 1) {
    searchResults.innerHTML = "";
  }

  const results = data.results;

  results.map((result) => {
    const imageWrapper = document.createElement("div");
    imageWrapper.classList.add("search-result");
    const image = document.createElement("img");
    image.src = result.urls.small;
    image.alt = result.alt_description;
    const imageLink = document.createElement("a");
    imageLink.href = result.links.html;
    imageLink.target = "_blank";
    imageLink.textContent = result.alt_description;

    imageWrapper.appendChild(image);
    imageWrapper.appendChild(imageLink);
    searchResults.appendChild(imageWrapper);
  });

  page++;

  if (page > 1) {
    showMoreButton.style.display = "block";
  }
}

form.addEventListener("submit", (event) => {
  event.preventDefault();
  page = 1;
  searchImages();
});

showMoreButton.addEventListener("click", () => {
  searchImages();
});

document.addEventListener("keypress",()=>{
   if("keypress"===13){
      searchImages()
   }
})
```
