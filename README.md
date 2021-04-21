Upgrade Drupal 8 > 9 in 20 Minutes
====

This repository contains an example Drupal 8 application to be used for the "Upgrade Drupal 8 > 9 in 20 Minutes" workshop.

To upgrade this site to Drupal 9, proceed to the following directions.

Workshop Walkthrough
===

1. Open CLI pane in the IDE browser tab.
   ![image](https://user-images.githubusercontent.com/539205/115598056-fd6dc600-a2a7-11eb-9b07-f1e365898981.png)
1. In the CLI pane of the Cloud IDE tab, Run:
   ```
   git clone https://github.com/grasmash/drupal8to9-upgrade .
   composer install
   drush site-install -y
   ```
1. Run `composer require drupal/upgrade_status`
1. Run `drush pm-enable upgrade_status -y`
1. Run `drush user-login` and cmd+click the link.
1. Visit `/admin/reports/upgrade-status` on the Drupal site. Reports => Upgrade Status.
  ![image](https://user-images.githubusercontent.com/539205/115598426-6bb28880-a2a8-11eb-996e-f1e6ca758b79.png)
1. Open composer.json in the IDE.
  ![image](https://user-images.githubusercontent.com/539205/115598302-41f96180-a2a8-11eb-8896-bba917745afa.png)
1. Change:
   ```
   "drupal/core-composer-scaffold": "^8.9.0",
   "drupal/core-recommended": "^8.9.0",
   ```
   To:
   ```
   "drupal/core-composer-scaffold": "^9.2.0",
   "drupal/core-recommended": "^9.2.0",
   ```
1. Run:
   ```
   composer update
   drush cache-rebuild
   drush updatedb
   ```
1. You're done!
