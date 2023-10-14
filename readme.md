# Translate WordPress Themes and Plugins with WP i18n Tools

## Table of Contents

- [Introduction](#introduction)
- [Features](#features) 
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Install and Set Up a Text Editor](#install-and-set-up-a-text-editor)
- [Internationalize Your Plugin](#internationalize-your-plugin)
- [Make tools folder](#make-tools-folder)
- [Navigate to Your project Directory](#navigate-to-your-project-directory)
- [Generate the POT File](#generate-the-pot-file)
- [Review and Customize the POT File](#review-and-customize-the-pot-file)
- [Prepare for Localization](#prepare-for-localization)
- [Compile Translations](#compile-translations)
- [Load Translations in Your Plugin](#load-translations-in-your-plugin)
- [Test Your Translations](#test-your-translations)
- [Contributing](#contributing)

## Introduction

This repository contains a set of tools and resources to help you translate WordPress themes and plugins using WP i18n (Internationalization) tools. Proper translation and localization are crucial for making your WordPress projects accessible to a global audience. This README provides an overview of the project and how to get started with it.

## Features

- Streamlined translation process for WordPress themes and plugins.
- Integration with WP i18n tools for a seamless workflow.
- Easily customizable translation templates.
- Cross-platform support for Windows, macOS, and Linux.

## Getting Started

Follow these steps to get started with translating WordPress themes and plugins using WP i18n Tools.

## Prerequisites
To create a language POT (Portable Object Template) file for your WordPress plugin, you'll need to extract translatable strings from your plugin's code and then generate the POT file. Here's a step-by-step guide:

## Install and Set Up a Text Editor
1. Install and Set Up a Text Editor: You can use any code editor or integrated development environment (IDE) to work on your plugin files. Make sure you have a suitable text editor installed.

## Internationalize Your Plugin
2. Internationalize Your Plugin: To make your plugin translatable, you need to wrap the strings you want to translate with translation functions like __() or _e(). For example:

`$text = __('This is a translatable string.', 'your-plugin-text-domain');`
Replace 'your-plugin-text-domain' with the unique text domain for your plugin.

## Make tools folder
3. Make tools folder `tools` on you project root folder `domain.test/tools` the put all `WP-i18n` files form git repo.
```
Project Root
├── domain.test
│ ├── tools
│
├── wp-admin
│
├── wp-content
│ ├── themes
│ ├── plugins
│ │ └── PLUGIN-FOLDER
│ │ └── languages
│ │ ├── PLUGIN-FOLDER.pot
│ │ ├── your-plugin-fr_FR.po
│ │ └── your-plugin-fr_FR.mo
│
├── wp-includes
```

## Navigate to Your project Directory
4. Navigate to Your project Directory: Open your command prompt or terminal, and navigate to your WordPress directory. For example:

`cd /path/to/your-project/tools`

## Generate the POT File
5. Generate the POT File: Use the wp i18n make-pot command to create the POT file. Replace `your-plugin-text-domain` or your-theme-text-domain with your actual text domain:

Command for theme
```
php makepot.php wp-theme ../wp-content/themes/THEME-FOLDER ../wp-content/themes/THEME-FOLDER/languages/THEMESLUG.pot
```


Command for plugin
```
php makepot.php wp-plugin ../wp-content/plugins/PLUGIN-FOLDER ../wp-content/plugins/PLUGIN-FOLDER/languages/THEMESLUG.pot
```

This command will scan the PHP files in your plugin directory for translatable strings and create a POT file in the languages directory.

## Review and Customize the POT File
6. Review and Customize the POT File: Open the generated your-plugin.pot file using your text editor. You can add additional information like comments and descriptions for translators.

## Prepare for Localization
7. Prepare for Localization: You need to provide translations for different languages. Create .po files for each language you want to support. For example, you can create your-plugin-fr_FR.po for French translations.

## Compile Translations
8. Compile Translations: After making translations, you need to compile them into .mo files using translation tools like Poedit. These .mo files should have the same name as your .po files (e.g., your-plugin-fr_FR.mo).

## Load Translations in Your Plugin
9. Load Translations in Your Plugin: To load the translated strings in your plugin, use the load_plugin_textdomain() function in your plugin file:

```
load_plugin_textdomain('your-plugin-text-domain', false, dirname(plugin_basename(__FILE__)) . '/languages');
```

## Test Your Translations
10. Test Your Translations: Install your plugin on a WordPress site, and change the site's language to the language for which you've created translations. Make sure the translations are working correctly.

That's it! You've created a POT file and set up translations for your WordPress plugin. Users will now be able to use your plugin in their preferred languages.

Contributing
We welcome contributions from the community. If you'd like to contribute to this project, please follow these guidelines:

Fork the repository and create a new branch for your feature or bug fix.
Make your changes and ensure that the code passes any existing tests.
Write clear and concise commit messages.
Submit a pull request.
