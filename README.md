# jquery-disqus
Just a simple snippet to get you going loading Disqus, including multiple threads on a page.

## Purpose

I needed to a simple way to load Disqus on a page, where multiple different Disqus threads might be needed. Specifically, it was a bunch of lightboxes that could be opened, each representing a unique resource, that each needed their own thread. Disqus's default example for embedding Disqus is only for loading one thread on a page. See here: https://help.disqus.com/customer/portal/articles/472097-universal-embed-code.

This is just a very lightweight script and example. Please modify it to your own needs. And refer to the Disqus documentation for the latest info on how to use Disqus. This example won't work if you haven't configured a Disqus account with a site. https://help.disqus.com/customer/portal/articles/1243156-developer-documentation

## Install

Look to the example HTML for how it's set up. You need jQuery, and to set two global variables: `disqusShortName` which is the "short name" identifier for your Disqus site, and `disqus_config` which will be configured at the time you load Disqus. And of course, load `jquery-disqus.js`.

## Usage

The target where Disqus loads is an element with a class of "disqus-container". On this element, include 3 data attributes: `data-disqus-url` for what URL the thread is for, `data-disqus-id` for the unique identifier you want to use for the thread, and `data-disqus-title` for what title to pass to Disqus for this thread. Eg:

    <div class="disqus-container" data-disqus-url="http://www.example.com/" data-disqus-id="some-unique-id" data-disqus-title="Example Title"></div>
    
Now, when you trigger a `loadDisqus` event on this element, it will load the thread. Eg: `$('.disqus-container').trigger('loadDisqus');`. You can have multiple `.disqus-container` elements on the page. Simply trigger `loadDisqus` on whichever one you want, and the thread element will be moved to it and reload with the data on the `.disqus-container`.

See the example: http://htmlpreview.github.io/?https://github.com/timothyshaw/jquery-disqus/blob/master/example.html

## Feedback

Hope you find this useful! Feel free to comment or suggest changes.
