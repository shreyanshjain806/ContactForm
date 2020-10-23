# ContactForm
Created with Html, Css, PHP, Bootstrap, jQuery
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CONTACT FORM DESIGN</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
    <div class="Contact-Title">
        <h1>Say HELLO </h1>
        <h2>We are always here to serve you</h2>

    </div>
    <div class="contact-Form">
        <form id="contact-Form" method="post" action="index.php">
            <input name="name" type="text" class="form-control" placeholder="Your Name" required>
            <br>
            <input name="email" type="email" class="form-control" placeholder="Your email" required>
            <br>
            <textarea name="message" class="form-control" placeholder="Message" cols="10" rows="4" required></textarea>
            <br>

            <input type="submit" class="form-control submit" value="SEND MESSAGE">





        </form>

    </div>
</body>
</html>

body{
    margin: 0;
    padding: 0;
    text-align: center;
    background: linear-gradient(rgba(0 , 0, 50 , 0.5),rgba(0 ,0 ,50, 0.5)),url(pic1.jpg);
    background-size: cover;
    background-position: center;
    font-family: sans-serif;
}

.Contact-Title
{
    margin-top: 100px;
    color:#fff;
    text-transform: uppercase;
    transition: all 4s ease-in;
}
.Contact-Title h1{
    font-size: 32px;
    line-height: 32px;
}
.Contact-Title h2{
    font-size: 16px;
}

.form
{
    margin-top: 50px;
    transition: all 4s ease-in-out;
}

.form-control
{
    width: 600px;
    background: transparent;
    border: none;
    outline: none;
    border-bottom: 1px solid gray;
    color: #fff;
    font-size: 18px;
    margin-bottom: 16px;

}

input{
    height: 45;
}
form .submit
{
    background: #ff5722;
    border-color: transparent;
    color: #fff;
    font-size: 20px;
    font-weight: bold;
    height: 50px;
    margin-top: 20px;
}

form .submit:hover
{
    background-color: #f44336;
    cursor: pointer;
}

<?php 
$name = $_POST['name'];
$visitor_email=$_POST['email'];
$message=$_POST['message'];


$email_from="abc@gmail.com";
$email_subject="new_form submission";
$email_body = "user name: $name.\n"."user Email:$visitor_email.\n"."user Message: $message.\n";

$to = "xyz@gmail.com";
$headers = "from: $email_from\r\n";
$headers .="reply-to: $visitor_email \r\n";

mail($to,$email_subject,$email_body,$headers);

header("location: index.html");

?>
