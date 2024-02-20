        THIS MODULE IS FOCUSED ON LARAVEL'S BREEZE IN-BUILT AUTHENTICATION SYSTEM

It explains the appropriate steps to take when integrating with the system, from installation , to integration, to Application and Use.

These afformentioned steps will be documented in this ReadMe.md section for future references


<!-- STEPS: -->
        BASE 1:  INSTALLATION / DATABASE MIGRATION AND MODEL

1. Instalattion : INSTALL Laravel package from php composer, a package that well suits your current PHP pre-installed .exe in your device, check Laravel documentation (laravel.com) to know this, but its best required you download the most recent PHP and Laravel Package, 
As of this case-study (BreezeAffair); the laravel 9. was used.

2. Create laravel project:  After installation from php composer, You can navigate into the directory in which you want to have your laravel application saved in you device, open git-bash and create a new laravel project with the command "composer create-project laravel/laravel AppName", where AppName refers to whatever name of your intended Project.

3. Breeze Instalation: we then want to get LARAVEL BREEZE installed in our project, this only takes a few commands to get completed, the commands would be ran in our IDE's Terminal. as in this case-study, IDE used is VSCODE.  (ofcourse other IDEs exist example: PHP STORM. )

4. Breeze Installation complete: In the opened terminal, we want to use these sets of command to get breeze installed and integrated into our app
    - composer require laravel/breeze --dev     //'this is for composer to install breeze in your laravel project//
    - php artisan breeze:install              // This next command will prompt yo to choose your preferred fron end stack, which in this case study, we chose BLADE //
    - php artisan migrate 
    - npm install              //Apparently we also need to install NODE , but before this can work, make sure you have Node pre-installed in your device and it is accessible to the Terminal //
    - npm  run dev       // This line completes theinstallation process of all the required stack including BLADE / VITE etc for Breeze Front-End.

5. After this is set, you then want to create a database system to be linked to your project, in this case-study, we make use of MySql Database. This is easily done by creating a table, and giving it same name in the '.env' file space for database. (see the laravel documention to understand more)
// Link the database created to your laravel project

6. Migrate to database:  After specifying our database in the '.env' file (DB_DATABASE = 'database_name'), we then want to run the artisan command to confim the link   // php artisan migrate //  -----  if this successfully migrates, we should see some new tables in the said new DATABASE.

7. Create Migrations: We can also create our own migrations, to which these authentications / gaurds / middlewares will be added to
    in this case - Student, Admin , Editor was used.
    ##commands -- //php artisan make:migration Student // -- e.t.c

8. Create corresponding model :  Consequently, a model is required for each migration created, hence we run commands to create the required MODELS      ##commands -- //php artisan make:model Student // -- e.t.c

9. Edit new migration files : ensure that the new migrations created with the commands in (7.) have adeqaute columns and datatypes to the kind of data to be saved in them when the table are to be created {schema::create ...} 

10. Edit new model files: ensure that the new models created with the commands in (8.) have the correct 'FILLABLE'-> this is an array of required data to be passed to the db.



                BASE 2: SEEDING DATA INTO THE DATABASE

        Seeding into the database simply means, having to put in some data into the database the right way, this action limits possible error to be encountered in the course of the project.

1. Creating Factories: the first step to seeding is creating factories, to tell the database seeder what to seed in. Quite interesting as it has to allign with the Model name created, the FACTORY file is located in the 'database' FOLDER where you also have the 'migrations' and 'seeders' file.

2. Factories command: to create factories we use the //php artisan make:factory Student //  -- etc. NOTE. that the naming convention must match with the models.

3. Factory data: when the factory file is created, '










<!-- <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 2000 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**
- **[WebReinvent](https://webreinvent.com/?utm_source=laravel&utm_medium=github&utm_campaign=patreon-sponsors)**
- **[Lendio](https://lendio.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT). -->
