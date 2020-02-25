# Cypress-Vetty
CES flow
describe('CES Test Cases', function(){ 

   

beforeEach(() => { 

cy.visit('https://stgapplicant.vetty.co/login') 

}) 

   

it('Login with Valid Email Id and Invalid Password', function(){ 

cy.get('#email').type('raqalyc@getnada.com') 

cy.get('#ssn').type(12345678).should('have.value', 123456) //wrong password 

cy.get('.form-control').click() 

cy.wait(10000) 

}) 

   

it('Login with Valid Email Id and Password, fill the details and redirected to VP', function(){ 

cy.get('#email').type('raqalyc@getnada.com') 

cy.get('#ssn').type('123456') 

cy.get('.form-control').click() 

cy.wait(10000) 

cy.get('#middleNameCheck').click() 

cy.wait(2000) 

cy.get('#street').type('26, Maple street') 

cy.get('#zip').type(123456) 

cy.wait(5000) 

cy.get('body > app-root > div > app-applicant-details > div > div > div > app-background-check > form > div > div:nth-child(2) > div:nth-child(1) > div > div > div > input').type('02/05/1996') 

cy.wait(2000) 

cy.get('#ssn').type(235345345) 

cy.get('#phone').type(1234567889) 

cy.wait(2000) 

cy.get('[style="padding : 0px 8px 0px 13px;"] > .form-label > div').last().click() 

cy.wait(3000) 

cy.get('.white-btn').click() 

cy.wait(5000) 

cy.get('input').click() 

cy.wait(2000) 

cy.get('.btnDefault').click() 

cy.wait(5000) 

cy.get('input').click() 

cy.wait(2000) 

cy.get('.btnDefault').click() 

cy.wait(5000) 

cy.get('input').last().click() 

cy.wait(2000) 

cy.get('.btnDefault').click() 

cy.wait(5000) 

cy.get('canvas') 

.click(80, 75) 

cy.wait(2000) 

cy.get('#printedName').type('John Devine') 

cy.get('.discloser > input').click() 

cy.wait(2000) 

cy.get('.btnDefault').click() 

cy.wait(10000) 

cy.get('.btnReview').click() 

cy.wait(5000) 

cy.get('.bottomSection > input').click() 

cy.get('.btnBottomNevigation > .btnDefault').click() 

   

//after completing the test, create new applicant and after login run this test to see the result 

}) 

   

it('Login but do not fill complete details and not able to redirect to VP', function(){ 

cy.wait(5000) 

cy.get('#email').type('pejyr@getnada.com') 

cy.get('#ssn').type('123456') 

cy.get('.form-control').click() 

cy.wait(10000) 

cy.get('#street').type('26, Maple street') 

cy.get('#zip').type(123456) 

cy.wait(5000) 

cy.get('body > app-root > div > app-applicant-details > div > div > div > app-background-check > form > div > div:nth-child(2) > div:nth-child(1) > div > div > div > input').type('02/05/1996') 

cy.wait(2000) 

cy.get('[style="padding : 0px 8px 0px 13px;"] > .form-label > div').click() 

cy.wait(3000) 

cy.get('.white-btn').click() 

//Not filling SSN, phone number and middle name details in Background page 

   

}) 

   

}) 
