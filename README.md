# imposejs
new javascript testing framework

With impose.js, I want to make sure that the testing must be fun and imposed on every code we write. I have some ideas which I am going to write here on this readme file.

Important concepts in a testing framework are:

Data setup
Assertions - use chai.js
Mocks - use sinon.js
Dependencies
Use cases

The idea of this framework is to reuse the test data and store it for future invocations. The storing of the data will serve as two purpose:
	1. It will make future invocations faster.
	2. Stored data can be used as mock data in future invocations.

Another Important factor is that every service call which makes a server side call has to have a mock data attached to it. This mock data will always be returned when called from testcases.  

User must be able to see the invocation path and the data flown from one invocation to another. 
User must be able to add a break point not on the basis of line but on the basis of values of variables and also based on various other conditions.

Just imagine:

You are writing a class or service or anything in JavaScript. 
This class or service has some functions which you want to test. 

/**
	@Testable(int=3, int=6)
	@Returns(int=9)
*/
function addTwoNumbers(let x, let y){
	
}

Here we just want to define that the method addTwoPoints 
	1. will be tested. - will always be tested
	2. Accepts two parameters which are of type int: Throws an assertion error if data you pass is of any type but int. 
	3. Mocks data as 3 and 4 - these values are assigned to the parameter when the function is called.
	4. The output of the method should be 9 - Throws an assertion error if the returned error is something else than 9.


/**
	@Testable
	@Returns
	@NeedsOutputFrom fileName.methodName
*/
function addTwoPoints(let obj){
	
}

This means before running this method, fileName.methodName should be run whose output will act as input to this function. 

/**
	@Testable(obj2={})
	@Returns
	@NeedsParamFrom fileName.methodName obj1 
*/
function addTwoPoints(let obj1, let obj2){
	
}

This means param obj1 is returned from the methodName
And param obj2 is assigned as literal 

/**
	@Testable(obj2=otherFile.otherMethod
	@Returns
	@NeedsParamFrom fileName.methodName obj1 
*
*/
function addTwoPoints(let obj1, let obj2){
	
}

This means param obj1 is returned from the methodName1
And param obj2 is the output of otherFile.otherMehod 

