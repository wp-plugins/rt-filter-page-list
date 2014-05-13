=== RT Filter Page List ===
Contributors: roytanck
Donate link: http://www.roytanck.com/
Tags: pages, widget, filter, folding, accordion, menu
Requires at least: 3.4.2
Tested up to: 3.9
Stable tag: 0.8
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Hooks into WordPress core function wp_list_pages, and removes pages from the generated list that are not part of the current navigation path.

== Description ==

Hooks into WordPress core function `wp_list_pages`, and removes pages from the generated list that are not part of the
current navigation path. This creates an accordion navigation effect, and is an alternative approach to the CSS-based
way suggested in the [Codex](http://codex.wordpress.org/Function_Reference/wp_list_pages#Markup_and_styling_of_page_items).

By removing unneeded HTML elements server-side, page size is reduced, and client-side rendering will usually be faster.
This is especially true for older browsers, and sites with a large number of published pages.

This plugin is inended to be usd with the "pages" widget that comes with WordPress, or any navigation element that uses
`wp_list_pages`.

Please note that since this plugin uses the `wp_list_pages` hook, the filtering will take place anywhere `wp_list_pages`
is used. This includes menu locations to which no custom menu is assigned. Please make sure all your menu locations
have a custom menu assigned to them to avoid unexpected behavior.

This plugin requires the PHP DOMDocument extension, and PHP5.

== Installation ==

1. Upload the folder `rt-filter-page-list` to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. No further configuration required

== Frequently Asked Questions ==

= After activating the plugin, there's no new options page =

This plugin works transparently in the background, and does not need any configuration. It simply modifies the
behavior of the WordPress function `wp_list_pages` wherever that function is used in your theme or widgets.

= Why would I use this instead of hiding pages through CSS? =

This is meant for cases where the pages menu contains a large number of pages, or where the target browser is slow
(e.g. IE7/8). Or both. This plugin can reduce the pages listing returned by WordPress by up to 99%.

= Will this make my site slower? =

Since the filtering is done server-side, your site's pages might take slightly longer to generate. However, they will
probably also be smaller (in terms of file size), and thus take less time to download. On sites where pages are cached,
the effect should be negligable.

= It's not clear which page is currently selected =

This plugin does not include CSS styles to highlight the currently selected page, its ancestors, or it children.
Ideally, your theme should take care of this.

== Screenshots ==

1. This screen shot description corresponds to screenshot-1.(png|jpg|jpeg|gif). Note that the screenshot is taken from
the /assets directory or the directory that contains the stable readme.txt (tags or trunk). Screenshots in the /assets 
directory take precedence. For example, `/assets/screenshot-1.png` would win over `/tags/4.3/screenshot-1.png` 
(or jpg, jpeg, gif).
2. This is the second screen shot

== Changelog ==

= 0.8 =
* Initial release, based on 'proven technology' from a client project.
