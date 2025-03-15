Follow these steps to create a JavaScript variable in GTM to get the total quantity of products from the data layer:

Step 1: Open Google Tag Manager
Log in to your Google Tag Manager account.
Select the GTM container where you want to add this variable.
Step 2: Create a New Variable
Navigate to the Variables tab.
Click New to create a new variable.
Set the variable type as Custom JavaScript.
Step 3: Add the JavaScript Code
Copy and paste the following code into the Custom JavaScript field:

javascript
Copy
Edit
function() {
  var products = {{dlv - ecommerce.cart_contents.products}}; // Replace with your actual data layer variable
  if (!products || !Array.isArray(products)) return 0;

  return products.reduce((total, product) => total + (parseInt(product.quantity) || 0), 0);
}
Click Save and name the variable, e.g., Total Cart Quantity.

Step 4: Use the Variable in GTM
You can now reference this variable in tags, triggers, or other GTM configurations using {{Total Cart Quantity}}.
Use it in event tracking, Google Analytics eCommerce tracking, or Google Ads conversion tracking.
Step 5: Test in Preview Mode
Click Preview in GTM and navigate to your website.
Open Google Tag Assistant and check if the variable returns the correct cart quantity.
If everything works correctly, Publish the changes.
