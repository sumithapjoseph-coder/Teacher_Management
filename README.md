# TeacherManagementApp

A simple **ASP.NET Core MVC** application for managing teachers, integrating with a **remote API** for CRUD operations.
Includes **authentication module** (login/register) and a **Teachers module** (view/add/edit/delete teachers) as per Ortez Infotech’s machine test requirements.

---

## Table of Contents

* [Features](#features)
* [Technologies](#technologies)
* [Setup & Run](#setup--run)
* [Folder Structure](#folder-structure)
* [API Integration](#api-integration)
* [Author](#author)

---

## Features

1. **Authentication Module**

   * Registration page (Name, Email, Password)
   * Login page (Email, Password)
   * Redirects to Teachers module after successful login

2. **Teachers Module**

   * View all teachers
   * View teacher details
   * Add a new teacher
   * Edit existing teacher
   * Delete teacher

3. **API Integration**

   * Uses `HttpClient` to call remote API
   * Serializes / deserializes JSON payloads using `System.Text.Json`

4. **Validation**

   * Basic client-side and server-side validation
   * Proper error handling

---

## Technologies

* ASP.NET Core 7 MVC
* Razor Views
* C#
* HttpClient
* JSON (System.Text.Json)
* Bootstrap (optional, for simple UI styling)

---

## Setup & Run

1. **Clone the repository**

```bash
git clone <your-repo-link>
cd TeacherManagementApp
```

2. **Open in Visual Studio**

3. **Restore NuGet packages**

   * Visual Studio should automatically restore packages on build

4. **Run the project**

   * F5 or `Ctrl+F5`
   * The default route opens `/Account/Login`

5. **Register a new user**

   * After registration, login to access Teachers module

---

## Folder Structure

```
TeacherManagementApp/
│
├── Controllers/
│   ├── AccountController.cs
|   ├── HomeController.cs
│   └── TeachersController.cs
│
├── Models/
│   ├── AuthResponseDto.cs
│   ├── LoginDto.cs
│   ├── RegisterDto.cs
│   ├── Teacher.cs
│   ├── TeacherCreateDto.cs
│   └── ErrorViewModel.cs
│
├── Services/
│   ├── AuthService.cs
│   └── TeacherService.cs
│
├── Views/
│   ├── Account/
│   │   ├── Login.cshtml
│   │   └── Register.cshtml
│   └── Teachers/
│       ├── Index.cshtml
│       ├── Create.cshtml
│       ├── Edit.cshtml
│       └── Details.cshtml
│
├── wwwroot/
├── Program.cs
└── README.md
```

---

## API Integration

* **Base URL:** `http://demoapimachinetest.ortezerp.in/`
* **Authentication APIs**

  * `POST /api/Auth/register` – Register user
  * `POST /api/Auth/login` – Login user
* **Teacher APIs**

  * `GET /api/Teachers` – Get all teachers
  * `GET /api/Teachers/{id}` – Get teacher by ID
  * `POST /api/Teachers` – Add new teacher
  * `PUT /api/Teachers/{id}` – Update teacher
  * `DELETE /api/Teachers/{id}` – Delete teacher

**Note:** For adding a teacher, use `TeacherCreateDto` without the `Id` field.
