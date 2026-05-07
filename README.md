<div align="center">

# 🌍 Tour Management System

**`Discover · Book · Explore`**

<br/>

[![PHP](https://img.shields.io/badge/PHP-8892BF?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)](https://jquery.com/)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

<br/>

> A **full-stack web application** to browse, book, and manage tour packages — with a dedicated **Admin Panel** for complete backend control.

</div>

---

```
  ✈️  User lands on homepage
       │
       ├──▶  🗺️  Browse Tour Packages
       │          │
       │          └──▶  📋  View Package Details
       │                     │
       │                     └──▶  📅  Select Dates & Book
       │                                │
       │                                └──▶  🎟️  Ticket Issued
       │
       ├──▶  🔍  Check Availability
       ├──▶  📬  Submit Enquiry
       └──▶  👤  User Profile & Tour History
```

---

## ✨ Feature Highlights

<table>
<tr>
<td width="50%">

### 👤 User Panel
| Feature | Page |
|---|---|
| 🏠 Homepage with live packages | `index.php` |
| 📦 Browse all packages | `package-list.php` |
| 🔎 Package details + booking form | `package-details.php` |
| 📅 Check tour availability | `check_availability.php` |
| 🎟️ View issued tickets | `issuetickets.php` |
| 📜 Tour booking history | `tour-history.php` |
| 📬 Submit an enquiry | `enquiry.php` |
| 👤 Edit user profile | `profile.php` |
| 🔐 Login / Register / Logout | `includes/` |
| 🔑 Change & forgot password | `change-password.php` |
| 🙏 Thank you confirmation | `thankyou.php` |

</td>
<td width="50%">

### 🛠️ Admin Panel
| Feature | Location |
|---|---|
| 📊 Admin Dashboard | `admin/` |
| 📦 Manage Tour Packages | `admin/` |
| 📋 View & manage bookings | `admin/` |
| 🎟️ Issue tickets to users | `admin/` |
| 📬 Manage enquiries | `admin/` |
| 👥 Manage registered users | `admin/` |
| 🖼️ Upload package images | `admin/pacakgeimages/` |
| 🔑 Admin authentication | `admin/` |

</td>
</tr>
</table>

---

## 🗂️ Project Structure

```
Tour-Management-System/
│
├── 📄  index.php                 ← Homepage (featured packages, offers)
├── 📄  package-list.php          ← All tour packages listing
├── 📄  package-details.php       ← Package detail + booking form
├── 📄  check_availability.php    ← Tour date availability checker
├── 📄  issuetickets.php          ← View issued tickets
├── 📄  tour-history.php          ← User's past bookings
├── 📄  enquiry.php               ← Contact/enquiry form
├── 📄  profile.php               ← User profile management
├── 📄  change-password.php       ← Password change
├── 📄  forgot-password.php       ← Password recovery
├── 📄  logout.php                ← Session logout
├── 📄  thankyou.php              ← Post-booking confirmation
├── 📄  page.php                  ← Static page renderer
│
├── 📁  admin/                    ← Admin panel (dashboard, CRUD)
│   └── 📁  pacakgeimages/        ← Uploaded package images
│
├── 📁  includes/                 ← Shared PHP components
│   ├── config.php                ← DB connection (PDO)
│   ├── header.php                ← Navbar + session
│   ├── footer.php                ← Footer
│   ├── signin.php                ← Login modal
│   ├── signup.php                ← Register modal
│   └── write-us.php              ← Contact modal
│
├── 📁  css/                      ← Bootstrap, Font Awesome, animations
├── 📁  js/                       ← jQuery, Bootstrap JS, WOW.js
├── 📁  fonts/                    ← Custom web fonts
└── 📁  images/                   ← Static site images
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| **Backend** | PHP (PDO) | Server-side logic & DB queries |
| **Database** | MySQL | Packages, bookings, users, enquiries |
| **Frontend** | HTML5 + CSS3 | Page structure & styling |
| **UI Framework** | Bootstrap 3 | Responsive grid & components |
| **Interactivity** | jQuery + jQuery UI | AJAX, datepickers, modals |
| **Animations** | WOW.js + Animate.css | Scroll-triggered effects |
| **Icons** | Font Awesome | UI icons throughout |

---

## ⚙️ Installation & Setup

### Prerequisites
- **PHP 7.4+** with PDO extension enabled
- **MySQL 5.7+** or MariaDB
- **Apache** (XAMPP / WAMP / LAMP) or any PHP-compatible server

---

### Step 1 — Clone the Repository

```bash
git clone https://github.com/slshree1/Tour-Management-System.git
```

Move to your server's web root:

```bash
# XAMPP (Windows)
cp -r Tour-Management-System/ C:/xampp/htdocs/

# LAMP (Linux)
cp -r Tour-Management-System/ /var/www/html/
```

---

### Step 2 — Create the Database

1. Open **phpMyAdmin** or your MySQL client
2. Create a new database:

```sql
CREATE DATABASE tour_management;
```

3. Import the provided SQL file:

```bash
mysql -u root -p tour_management < database/tour_management.sql
```

---

### Step 3 — Configure Database Connection

Edit `includes/config.php` and update with your credentials:

```php
<?php
$host     = 'localhost';
$dbname   = 'tour_management';
$username = 'root';
$password = '';

try {
    $dbh = new PDO("mysql:host=$host;dbname=$dbname", $username, $password);
    $dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Connection failed: " . $e->getMessage());
}
?>
```

---

### Step 4 — Launch the Application

Start your Apache and MySQL services, then open in a browser:

```
http://localhost/Tour-Management-System/
```

**Admin Panel:**
```
http://localhost/Tour-Management-System/admin/
```

---

## 🗄️ Database Tables

| Table | Description |
|---|---|
| `tbltourpackages` | Stores all tour packages (name, type, location, price, image) |
| `tblbooking` | User bookings with dates, status, and comments |
| `tblusers` | Registered user accounts |
| `tblenquiry` | Customer enquiries |
| `tbltickets` | Issued tickets per booking |
| `tblpages` | Static CMS pages |

---

## 📸 Pages at a Glance

| 🌐 Page | 📝 Description |
|---|---|
| **Homepage** | Featured packages, offers, stats (80K enquiries, 7Cr+ bookings) |
| **Package List** | Grid of all available tours with price & location |
| **Package Details** | Full info + date picker + booking form |
| **Tour History** | Logged-in user's past and upcoming bookings |
| **Issued Tickets** | Downloadable/viewable tickets per booking |
| **Admin Dashboard** | Full CRUD for packages, bookings, users & enquiries |

---

## 🔐 Security Notes

> ⚠️ Before deploying to production, make sure to:
> - Move `includes/config.php` outside the web root or restrict access
> - Use environment variables for database credentials
> - Enable HTTPS on your server
> - Sanitize and validate all user inputs (PDO prepared statements already used ✅)
> - Set strong admin passwords

---

<div align="center">

---

🌏 **Explore the world, one package at a time.**

Built with 💙 using **PHP · MySQL · Bootstrap · jQuery**

*Give it a ⭐ if you found it useful!*

</div>
