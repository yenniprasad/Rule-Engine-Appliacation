
# Rule Engine Application by Y Durga Prasad 

## Application Overview 

This application functions as a rule engine that assesses user eligibility based on various attributes, including age, department, salary, and experience. It employs an Abstract Syntax Tree (AST) for representing and managing conditional rules, facilitating the dynamic creation, combination, and evaluation of rules.

## Features

- **Rule Creation:** Users can define rules using a string format, which is then transformed into an AST.
![Screenshot 2024-10-23 180143](https://github.com/user-attachments/assets/f6e841a6-1b63-425e-bc64-2b69dc166650)


- **Rule Combination:** Allows the merging of multiple rules into a singular AST to enable more intricate evaluations.

![Screenshot 2024-10-23 180237](https://github.com/user-attachments/assets/5a53e34a-336e-47dc-b634-9b416b79cbac)


- **Rule Evaluation:** Assesses whether the provided data aligns with the criteria set by the AST.

![Screenshot 2024-10-24 172215](https://github.com/user-attachments/assets/f12b450b-74ec-426f-837d-c67ebd5fcfc4)


- **Tree Visualization:** When defining or combining rules, a tree representation will be displayed for better understanding.

## Tech Stack

- **Backend:** Built with Node.js and Express.js
- **Database:** Utilizes MongoDB

## Getting Started

### Prerequisites

- Ensure Node.js and npm are installed.

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone "https://yenniprasad.github.io/Rule-Engine-Appliacation/"
   ```
2. **Install the Backend Dependencies**
   ```bash
   npm install
   ```
2. **Create a .env file and add ur Mongo_url**
   ```bash
   MONGO_URL=""
   ```
4. **Launch the Server**
   ```bash
   npm start
   ```

## API Endpoints

1. **Create a Rule**
   - **Endpoint:** `/api/create_rule`
   - **Method:** POST
   - **Request Body:**
     ```json
     {
       "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
       "ruleName": "Rule-1"
     }
     ```
   - **Note:** Ensure that there are appropriate spaces in the rule for accurate results. The rule should follow this format: 
   `variable operator value`
   - **Response:**
    <img src="https://github.com/user-attachments/assets/4f66d741-c025-45cd-b602-acc027f0a9c6" alt="Response Image" width="300" />

   
     
     
2. **Combine Rules**
   - **Endpoint:** `/api/rules/combine_rules`
   - **Method:** POST
   - **Request Body:**
   - **Response:**
   <img src="https://github.com/user-attachments/assets/908bbdc4-0d21-4a33-ac39-5a8041100b99" alt="Response Image" width="300" />



3. **Evaluate a Rule**
   - **Endpoint:** `/api/rules/evaluate_rule`
   - **Method:** POST
   - **Request Body:**
     ```json
     {
       "rule": { ... },
       "data": {
         "age": 35,
         "department": "Sales",
         "salary": 60000,
         "experience": 3
       }
     }
     ```
   - **Response:**
     ```json
     {
       "result": true
     }
     ```

## Running Tests

You can implement and execute tests to verify that everything is functioning as expected.
