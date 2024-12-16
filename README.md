# BookStore

## Opis biznesowy

BookStore to platforma e-commerce do sprzedaży książek, która oferuje dwa główne tryby użytkownika: **klienta** i **administrator**.

- **Klient**:
  - Przeglądanie dostępnych książek.
  - Przeglądanie szczegółów książek oraz kategorii.
  - Możliwość swobodnego wybierania książek, ale bez możliwości ich edytowania lub dodawania nowych.

- **Administrator**:
  - Rejestracja i logowanie przez Google.
  - Dodawanie nowych książek.
  - Edytowanie istniejących książek.
  - Przypisywanie książek do kategorii.
  - Zarządzanie całą bazą danych książek.

Platforma nie obsługuje płatności.

---

## Rozwiązania

- **System zarządzania książkami**: Umożliwia łatwe dodawanie, edytowanie oraz kategoryzowanie książek przez administratora.
- **Rejestracja przez Google**: Szybkie i bezpieczne logowanie za pomocą Google OAuth 2.0.
- **Panel administracyjny**: Pełna kontrola nad zawartością sklepu.

---

## Technologie

### Frontend
- **Blazor**: Tworzenie dynamicznego interfejsu użytkownika.
- **HTML5, CSS3, JavaScript**: Do ogólnych funkcji interfejsu i układów strony.

### Backend
- **ASP.NET Core**
- **Entity Framework**: ORM (Object-Relational Mapping) do pracy z bazą danych.
- **Google Authentication**: Logowanie przez OAuth 2.0.

### Baza danych
- **SQL Server**: Przechowywanie danych dotyczących książek, kategorii oraz użytkowników (adminów).

---

## Struktura bazy danych
<img src="/ReadMeInfo/Untiteled(1).png" alt="Data Base" width="300" height="200">

### Główne tabele:

#### **Tabela `AspNetRoles`**
- Przechowuje role użytkowników w systemie (np. „Admin”, „User”).
- **Pola**: `Id`, `Name`, `NormalizedName`, `ConcurrencyStamp`.

#### **Tabela `AspNetRoleClaims`**
- Przechowuje dodatkowe uprawnienia (claims) przypisane do ról.
- **Pola**: `Id`, `RoleId`, `ClaimType`, `ClaimValue`.

#### **Tabela `AspNetUsers`**
- Przechowuje dane użytkowników systemu.
- **Pola**: `Id`, `Name`, `Email`, `PasswordHash`, `UserName`, `PhoneNumber`, `TwoFactorEnabled`.

#### **Tabela `AspNetUserClaims`**
- Przechowuje dodatkowe uprawnienia (claims) użytkowników.
- **Pola**: `Id`, `UserId`, `ClaimType`, `ClaimValue`.

#### **Tabela `AspNetUserLogins`**
- Przechowuje informacje o metodach logowania użytkowników (np. Google).
- **Pola**: `LoginProvider`, `ProviderKey`, `UserId`.

#### **Tabela `AspNetUserRoles`**
- Łączy użytkowników z ich rolami.
- **Pola**: `UserId`, `RoleId`.

#### **Tabela `Categories`**
- Przechowuje kategorie produktów (np. książki, ubrania).
- **Pola**: `Category_Id`, `Name`, `DisplayOrder`.

#### **Tabela `Products`**
- Przechowuje informacje o produktach oferowanych w systemie.
- **Pola**: `Id`, `Title`, `Description`, `ISBN`, `Author`, `Price`, `CategoryReferenceId`, `ImageUrl`.

---

## Funkcje

### Tryb Klienta:
- Logowanie przez Google.
- Przeglądanie książek i szczegółów kategorii.

### Tryb Administratora:
- Logowanie przez Google.
- Dodawanie, edytowanie i usuwanie książek.
- Przypisywanie książek do kategorii.

---

## Wyzwania

- **Integracja Blazora z ASP.NET Core**: Trudności z synchronizacją komponentów Blazora z backendem.
- **Logowanie przez Google**: Wymagało konfiguracji API OAuth w Google Developers Console.
- **Zarządzanie bazą danych**: Normalizacja struktury danych pozwoliła na stworzenie skalowalnej bazy danych.

---

