- Software Project Developer 

- Specialized in PHP, MySQL, CSS, C++, Java, asp.net, Kotlin

- Mobile app - Android, iOS.

- Framework :
  
  * ASP.NET: is Microsoft Framework and one of the most used.
  * Symphony: PHP free software project.
  * Zend Framework: Open source framework for developing web applications and with PHP web services.
  * Laravel: One of the easiest open source frameworks to assimilate for PHP.
  * Django: open source web development framework written in Python.
  * Ruby on Rails: Open source web application framework written in the Ruby programming language.
  * Angular: open source framework developed in TypeScript and maintained by Google.

- Software editor :

  * Adobe Dreamweaver: is a code editor that supports syntax highlighting, code completion, real-time syntax checking, and code introspection.
  * Adobe Photoshop: is a raster graphics editor developed.
  * Adobe Ilustrator: is vector-based graphics software that lets you scale down your artwork for mobile screens or scale up to billboard size.
  * PhpStorm: PHP IDE and Code Editor from JetBrains
  * Atom: is the “hackable text editor for the 21st century”, according to its slogan.
  * Notepad++: is a text and source code editor for use with Microsoft Windows.
  * Sublime Text: for the whole project, it can automatically create an index for class, method, and function.
  * Eclipse: is an integrated development environment (IDE) which is used for almost every language using Plugins.
  * CodeLite:  is a free and open source IDE with support for PHP and Node.js (as pre-installed plugins).
  * Visual Studio Code: is a source-code editor made by Microsoft with the Electron Framework, for Windows, Linux and macOS
  * Android Studio: is used for developing apps on every type of Android device.


============================================================== Note setting ********

Starting LARAVEL 10

composer create-project laravel/10x-training

cd 10x-training


INTERFACE

composer require laravel/ui

php artisan ui bootstrap --auth

npm install && npm run build


DATABASE

Setting .env

php artisan migrate:status

php artisan migrate


=========================================

AKSES ONLY ID for auth protect

10x-training -> routes -> web

Route::middleware('auth:student`)->group( function () {
    Route::resource('products', ProductController::class);
});

BUAT TABLE DB

php artisan make:migration create_products_table --create=products

php artisan migrate:rollback

Php artisan migrate:status

Create Controller and Model

php artisan make:controller ProductController --resource --model=Product


LIVEWIRE

Composer require livelier/livewire
=======================================================
Include the assets in resources/view/layouts/app.blade.php - 

    @vite(['resources/sass/app.scss', 'resources/js/app.js'])
    @livewireStyles

        <main class="py-4">
            @yield('content')
        </main>
    </div>
    @livewireScripts
========================================================

Php artisan livewire:publish —config

Php artisan livewire:publish —assets

=======================================================

Add at composer.json —— line 38

        "post-autoload-dump": [
            "Illuminate\\Foundation\\ComposerScripts::postAutoloadDump",
            "@php artisan package:discover --ansi",
            "@php artisan vendor:publish --force --tag=livewire:assets --ansi"

=======================================================

laravel-permission

composer require spatie/laravel-permission

php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"

php artisan optimize:clear

php artisan migrate

========================================================

Set file - app/models/user.php

Add user model -  use HasRoles;

Add use - use Spatie\Permission\Traits\HasRoles;

=========================================================

composer require sentgine/authzone 

php artisan authzone:install

=========================================================

Set file - config/authzone.php

Line 50 - edit - 'layout_path' => 'sentgine.authzone.layouts',

Set layout - resources/views/sentgine/authzone/layouts/app.blade.php

Line 11 - edit - @vite(['resources/sass/app.scss', 'resources/js/app.js'])

============================================================

php artisan view:clear

composer dump-autoload




<!---
zsham/zsham is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
