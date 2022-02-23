## Laravel-Sweet-Alert

## About:
Laravel sweet alert is very usefull for display message. 

## Run below command for install sweet-alert package

```php

composer require realrashid/sweet-alert

```
## Now publish sweet alert:

```php

php artisan sweetalert:publish

```

## Include the script as below in the master layout. 
Because we are using the laravel ui package, we automatically have a master layout located in the resources/views/layouts/app.blade.php directory. Place the script above between the <body> ... </body> tags

```html
@include('sweetalert::alert')

```

## Go to App/Http/Controllers/Auth/RegisterController.php file:
to be like the example above and don't forget to 
```php
use RealRashid\SweetAlert\Facades\Alert;

protected function create(array $data)
    {
        $user = User::create([
            'name' => $data['name'],
            'email' => $data['email'],
            'password' => Hash::make($data['password']),
        ]);

        Alert::success('Congrats', 'You\'ve Successfully Registered');

        // or using toast

        // Alert::toast('You\'ve Successfully Registered', 'success');

        return $user;
    }
```

## Sweet alert for helper function:

```php

Alert::info('Info Title', 'Info Message');
Alert::warning('Warning Title', 'Warning Message');
Alert::error('Error Title', 'Error Message');
Alert::question('Question Title', 'Question Message');
Alert::image('Image Title!','Image Description','Image URL','Image Width','Image Height');
Alert::html('Html Title', 'Html Code', 'Type');

```
