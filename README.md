<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Trivexzen T-Shirts</title>
  <script src="https://checkout.razorpay.com/v1/checkout.js"></script>
  <style>
    body {
      background-color: #111827;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 0;
      padding: 0;
    }
    h1 { font-size: 2rem; margin-top: 2rem; }
    .product {
      margin: 2rem auto;
      width: 90%;
      max-width: 400px;
      background: #1f2937;
      border-radius: 12px;
      padding: 20px;
      box-shadow: 0 0 10px rgba(255,255,255,0.1);
    }
    img { width: 100%; border-radius: 12px; }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      color: white;
      font-weight: bold;
      margin: 10px;
      cursor: pointer;
    }
    .buy { background-color: #4f46e5; }
    .cod { background-color: #16a34a; }
  </style>
</head>
<body>
  <h1>TRIVEXZEN Premium T-Shirts</h1>
  <div class="product">
    <img src="https://via.placeholder.com/400x400?text=T-Shirt" alt="T-Shirt">
    <h2>Urban Classic Tee</h2>
    <p>₹799</p>
    <button class="buy" onclick="payNow(799)">Buy Now (Online)</button>
    <a href="https://wa.me/91XXXXXXXXXX?text=Hello%20I%20want%20Cash%20on%20Delivery%20T-shirt%20Order" target="_blank">
      <button class="cod">Cash on Delivery</button>
    </a>
  </div>

  <script>
    function payNow(amount){
      var options = {
        "key": "YOUR_KEY_ID", // 🔑 Razorpay Dashboard-ൽ നിന്നുള്ളത് ചേർക്കുക
        "amount": amount * 100,
        "currency": "INR",
        "name": "TRIVEXZEN",
        "description": "T-shirt Order",
        "handler": function (response){
          alert("Payment Successful! ID: " + response.razorpay_payment_id);
        },
        "theme": {
          "color": "#4f46e5"
        }
      };
      var rzp = new Razorpay(options);
      rzp.open();
    }
  </script>
</body>
</html>
