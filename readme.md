# Coding Standard for WordPress Plugins and Themes on Envato Market

[![Build Status](https://travis-ci.com/wpsh/wpcs-for-envato.svg?branch=master)](https://travis-ci.com/wpsh/wpcs-for-envato)

Automatically check for Envato [WordPress plugin](https://help.author.envato.com/hc/en-us/articles/360000481223-WordPress-Theme-Plugin-Requirements) and [theme coding requirements](https://help.author.envato.com/hc/en-us/articles/360000479946-WordPress-Theme-Coding-Requirements).


## Requirements

- [Composer](https://getcomposer.org)


## Setup

1. Add these coding standards as a [Composer development dependency](https://packagist.org/packages/wpsh/wpcs-for-envato) to your project:

	```bash
	composer require --dev wpsh/wpcs-for-envato
	```

2. Define a script in `composer.json` to run the checks:

	```json
	{
		"scripts": {
			"phpcs": "./vendor/bin/phpcs --standard=WPCSForEnvato --extensions=php",
			"phpcs-fix": "./vendor/bin/phpcbf --standard=WPCSForEnvato --extensions=php"
		}
	}
	```

	Use `composer cs` to run the coding standard checks and `composer csfix` to automatically fix some of the coding standard violations.


## Configuration

Add `phpcs.xml.dist` to your project root that provides additional configuration options:

```xml
<?xml version="1.0"?>
<ruleset name="WordPress coding standards for Envato">
	<rule ref="WPCSForEnvato"/>

	<!-- Specify a prefix that should be used for all global functions and variables. -->
	<rule ref="WordPress.NamingConventions.PrefixAllGlobals">
		<properties>
			<property name="prefixes" type="array">
				<element value="our_custom_prefix"/>
				<element value="tgmpa"/>
			</property>
		</properties>
	</rule>
</ruleset>
```

## Credits

Created by [Kaspars Dambis](https://kaspars.net).
