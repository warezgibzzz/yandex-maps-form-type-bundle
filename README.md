# YandexMapsFormTypeBundle

Set the latitude and longitude using Yandex Maps

## Installation

Add it-blaster/yandex-maps-form-type-bundle to your `composer.json` file and run `composer`

```json
...
"require": {
    "it-blaster/yandex-maps-form-type-bundle": "1.0.*"
}
...
```

Register the bundle in your `AppKernel.php`

```php
...
new Fenrizbes\YandexMapsFormTypeBundle\FenrizbesYandexMapsFormTypeBundle(),
...
```

Include bundle's scripts in your page:

```html
...
<script src="{{ asset('bundles/fenrizbesyandexmapsformtype/js/yandex_maps_widget.js') }}"></script>
...
```

## Usage

Just set the `yandex_maps` FormType for your field as follows:

```php
...
    ->add('coordinates', 'yandex_maps')
...
```

The type takes and returns an array with items `lat` for the latitude and `lng` for the longitude. So you need to
configure your database coordinates column as `OBJECT` or create the setter and getter for it on your model.

## Options

There are a few options that you can pass:

```php
...
    ->add('coordinates', 'yandex_maps', array(
        'width'   => 640,      // The map's width
        'height'  => 480,      // The map's height
        'default' => array(
            'lat' => 55.75319, // The default latitude value
            'lng' => 37.619953 // The default longitude value
        )
    ))
...
```

## Configuration

You can configure default values for type's options to avoid passing them every time:

```yml
...
fenrizbes_yandex_maps_form_type:
    size:
        width:  640
        height: 480
    default:
        lat: 55.75319
        lng: 37.619953
...
```
