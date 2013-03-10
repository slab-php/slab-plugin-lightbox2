slab-plugin-lightbox2
=====================

A [Slab](https://github.com/swxben/slab) plugin based on a version of [Lightbox2](http://lokeshdhakar.com/projects/lightbox2/). Additionally the following changes have been pulled in:

- jQuery 1.9.1 support - <https://github.com/lokesh/lightbox2/pull/35>


## Usage

Copy the `lightbox2` folder in to your application's `plugins` folder:

	/www
		/app
			/controllers
			/views
			/plugins
				/lightbox2
		/css
		/js
		/...

Include the css and js files in the application's default layout - `app/views/layouts/default.php` - or as appropriate. Note that lightbox2 depends on jQuery (1.9.1 with the changes made to the lightbox2 source).

	<html lang="en">
		<head>
			...
			<link href="<?php e($html->url('/lightbox2/lightbox_css')); ?>" rel="stylesheet">
		</head>
		<body>
			...
			<script src="<?php e($html->url('/js/jquery-1.9.1.min.js')); ?>"></script>
			<script src="<?php e($html->url('/lightbox2/lightbox_js')); ?>"></script>
		</body>
	</html?

Add the markup required for the lightbox gallery per [the Lightbox 2 documentation](http://lokeshdhakar.com/projects/lightbox2/) - this example constructs markup for a Twitter Bootstrap thumbnail gallery:

	<ul class="thumbnail">
		<?php foreach ($photos as $photo): ?>
			<a href="<?php e($html->url("/gallery/get_thumbnail/{$photo['id']}")); ?>" rel="lightbox[gallery]" title="<?php eh($photo['title']); ?>">
				<img data-src="<?php e($html->url("/gallery/get_photo/{$photo['id']")); ?>" alt="<?php eh($photo['title']); ?>"
			</a>
			<h3><?php eh($photo['label']); ?></h3>
			<?php e($html->markdown($photo['caption'])); ?>
		<?php endforeach; ?>
	</ul>


## License

###Lightbox2
by Lokesh Dhakar | [lokeshdhakar.com](http://www.lokeshdhakar.com)  | [twitter.com/lokeshdhakar](http://twitter.com/lokeshdhakar)  

####Information and support
For examples, downloads, and information on using Lightbox, visit the Lightbox2 homepage:  
[http://lokeshdhakar.com/projects/lightbox2/](http://lokeshdhakar.com/projects/lightbox2/)

For personal support issues and feature requests, visit the Lightbox forums:  
[http://lokeshdhakar.com/forums/](http://lokeshdhakar.com/forums/)

####License
Licensed under the Creative Commons Attribution 2.5 License - http://creativecommons.org/licenses/by/2.5/

* Free for use in both personal and commercial projects.
* Attribution requires leaving author name, author homepage link, and the license info intact.