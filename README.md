BootStrength.js
===========

A password strength plugin for Bootstrap. Based on Strength.js by @aaronlumsden (http://git.aaronlumsden.com/strength.js/)

#### Documentation

BootStrength.js is a fork of Strength.js originally forked to make it work nicely with Bootstrap. 

Its core was almost entirely rewritten to cater for:
* Instantiating multiple instances per page
* Allowing the definition of 'strength' to be manually defined at instantiation
* Dynamically adding an 'info' button to the right of the password field to reveal the password requirements (this is a replacement of the original 'Show Password' feature)

#### Demo
For a demo see http://bootstrength.lowlevel.co.za


#### Getting Started

##### Include the relevant files:

Firstly include jQuery, Bootstrap and the boot_strength js and css files. Place these before the `</head>` tag.
```
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css" integrity="sha512-dTfge/zgoMYpP7QbHy4gWMEGsbsdZeCXz7irItjcC3sPUFtf0kuFbDz/ixG7ArTxmDjLXDmezHubeNikyKGVyQ==" crossorigin="anonymous">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
  <link rel="stylesheet" href="css/boot_strength.css" type="text/css">

  <script src="https://code.jquery.com/jquery-2.1.4.min.js" type="text/javascript"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js" integrity="sha512-K1qjQ+NcF2TYO/eI3M6v8EiNYZfA95pQumfvcVrTHtwQVDG+aHRqLi/ETn2uB+1JqwYqVG3LIvdm9lj6imS/pQ==" crossorigin="anonymous"></script>
  <script src="js/boot_strength.js" type="text/javascript"></script>
```				

##### Create a password input field:

The 'password' field must have a unique ID, and you MUST add the 'boot_strength' class to the bootstrap 'form-group' div.
```
    <div class="form-group boot_strength">
     <label for="password">Please enter a new password</label>
     <input type="password" class="form-control" id="password" name="password" value=''>
    </div>
```

##### Instantiate the plugin for each element, including any option overrides where necessary:

Once you have created your password input field you will need to instantiate the plugin for each required input element.

Examples include:

```
 $(function(){

   $('#password').boot_strength({
    strength_minlength: 10,
    strength_required_special:3
   });

   $('#password2').boot_strength({
    strength_minlength: 9,
   });
 }); // end document.ready
```


#### Options

The password strength definition includes the following options:

<table>
	<thead>
		<tr>
			<th>Variable</th>
			<th>Default Value</th>
			<th>Description</th>
			<th>Valid Options</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>strength_minlength</td>
			<td>8</td>
			<td>The minimum length the password must be</td>
			<td>Positive integer</td>
		</tr>
		<tr>
                        <td>strength_required_upper</td>
                        <td>1</td>
                        <td>The number of required upper case characters</td>
                        <td>Positive integer</td>
                </tr>
		<tr>
                        <td>strength_required_lower</td>
                        <td>1</td>
                        <td>The number of required lower case characters</td>
                        <td>Positive integer</td>
                </tr>
		<tr>
                        <td>strength_required_digits</td>
                        <td>1</td>
                        <td>The number of required digit characters</td>
                        <td>Positive integer</td>
                </tr>
		<tr>
                        <td>strength_required_special</td>
                        <td>1</td>
                        <td>The number of required special characters</td>
                        <td>Positive integer</td>
                </tr>
	</tbody>
</table>
