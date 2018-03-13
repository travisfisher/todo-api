## Installation

```sh
git clone https://github.com/travisfisher/todo-api
cd todo-api
npm install
```

## Commands

Start API with JWT Authentication:

```sh
npm run start-auth
```

Start API without JWT Authentication:

```sh
npm run start
```

Either of these commands will start the API service on http://localhost:3000

## API Methods

Below are the set of methods that are available to you.

_Note that all POST methods are expected to be submitted as: **Content-Type: application/x-www-form-urlencoded**_

### POST /auth/login

Request body:

| Parameter Key | Type    | Required |
| ------------- | ------- | -------- |
| username      | String  | Yes      |
| password      | String  | Yes      |

**Response body:**

    {
      "accessToken": "...",
      "user": {
        "id": 1,
        "username": "john@smith.com",
        "password": "abc123",
        "first_name": "John",
        "last_name": "Smith"
      }
    }

### GET /tasks

**Response body:**

    [
      {
        "id": 1,
        "user_id": 1,
        "task": "Task 1",
        "complete": 0
      },
      {
        "id": 2,
        "user_id": 1,
        "task": "Task 2",
        "complete": 0
      },
      {
        "id": 3,
        "user_id": 1,
        "task": "Task 3",
        "complete": 0
      }
    ]

### GET /tasks/[id]

**Response body:** 

    {
      "id": 1,
      "user_id": 1,
      "task": "Task 1",
      "complete": 0
    }

### POST /tasks

**Request body:**

| Parameter Key | Type    | Required |
| ------------- | ------- | -------- |
| user_id       | Integer | Yes      |
| task          | String  | Yes      |
| complete      | 0 or 1  | Yes      |

**Response body:**

    {
      "id": 3,
      "user_id": 1,
      "task": "Task 3",
      "complete": 0
    }

### PUT /tasks/[id]

**Request body:**

| Parameter Key | Type    | Required |
| ------------- | ------- | -------- |
| user_id       | Integer | No       |
| task          | String  | No       |
| complete      | 0 or 1  | No       |

**Response body:**

    {
      "id": 3,
      "user_id": 1,
      "task": "Task 3",
      "complete": 1
    }


## Contributions

Feel free to submit pull requests, create issues or spread the word.