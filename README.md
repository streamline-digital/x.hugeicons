# x.hugeicons

These icons were created by the Hugeicons project.

https://hugeicons.com/icons

https://github.com/hugeicons/hugeicons-react

The icons were gathered using the client-side Javascript below to collect the URLs while scrolling the entire page and `wget` to download them.

```
// Create an array to store unique URLs
let imgUrls = [];

// Function to extract URLs from img src attributes
function extractImgUrls() {
  // Get all img elements in the document
  const imgElements = document.querySelectorAll('img[src]');
  imgElements.forEach(img => {
    // Get the URL from the src attribute
    const url = img.getAttribute('src');
    // Check if URL is not already in the array and it's not empty
    if (url && !imgUrls.includes(url)) {
      // Add the URL to the array
      imgUrls.push(url);
    }
  });
}

// Call the function initially to extract URLs from existing img tags
extractImgUrls();

// Attach an event listener to capture newly added img tags
document.addEventListener('DOMNodeInserted', extractImgUrls);
```

After saving the URLs to file:

```
wget -i data/urls.tsv
```
