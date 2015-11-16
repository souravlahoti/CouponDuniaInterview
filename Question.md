Q1. Using CSS properties alone, recreate this button: 
<br>
![alt text] (http://i.imgur.com/gnZnY.png).<br> Spend no longer than 15 minutes on it (this is not a time limit, but a measure to evaluate yourself), we don't expect it to be a perfect match. It's open book, feel free to hit Google but be prepared to explain your solution.

---

Q2. Please write the code for an object that allows us to register several different functions to execute a single common callback function. 

The purpose of the object is to execute all the registered functions and then, once ALL of them are finished, It should execute the defined callback function.

Once I call syncFuncs.start(), the syncFuncs object would start to execute all the registered functions asynchronously. Once the last one returns, it would finally execute the callback function.

I should also be able to define a maxmium time before the callback function executes. For example, if I define that as 3000 and it takes more than 3 seconds for all the registered ajax functions to return (after calling start()), it should proceed to execute the callback function even though the ajax functions have not finished returning.

To be clear, this code needs to be flexible, standalone, and reuseable. 

As a hint, you could do something along the following to register a function that makes an AJAX call to CouponDunia.

```javascript
syncFuncs.register(function () {
	$.ajax({
 		url: "http://www.coupondunia.in"
	})
 	 .always(function(){ 
	  syncFuncs.markDone();
     });
})
```

As you see above the function that is being registered communicates with the syncFuncs object to tell the syncFuncs object that it (the registered function) has finished executing (through the use of markDone).

You can assume that any function that we register will implement a call to markDone at some point within it.

---

Q3. We want to be able to pick our seats in a cinema hall. Given a seating arrangement create a visual seat picker. 
You can hardcode the seat map in your javascript. You should define the names of the categories i.e. gold, silver, bronze as well as the number of rows and seats per row in the specific category. For example you could create an array that tells you gold has 7 rows with 8 seats each, while silver has 5 rows with 7 seats each, and so on.
On the front end you should include a form that asks the user the number of tickets they are booking. Also, you need to mention booking category (gold, silver etc.). Then allow them to select the specific seats they want to book and split out the seat number and row (you can create a seat number/row scheme).
You should only allow people to book seats that are adjacent to each other (in other words one should not be allowed to book seat 1 and seat 3 without also booking seat 2). 
We should also prevent people from creating single seat silos unless there is no alternative. For example in a row of 4 seats, a user should not be allowed to book seats 2 and 3 because in that case seat 1 would be alone and seat 4 would be alone. He should be forced to book seats 1-2 or seats 3-4.
Please also make all of this look nice. We are judging you on the correctness of the functionality, the quality of the code, and the front-end smoothness.


