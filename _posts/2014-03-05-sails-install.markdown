---
layout: post
title:  "Sails Install"
date:   2014-03-05 09:25:56
categories: sails frontend install readme update
---

# Ahoy
### Adoreboard Website Sails application

1. Requires Node.js
2. Install Sails ```sudo npm -g install sails```
3. Create a new sails app with linker enabled ```sails new ahoy --linker```
4. Install Bower Globally ```npm install -g bower```
5. CD into ```cd assets/linker/```
6. Install Bootstrap with Bower ```bower install bootstrap```
7. Install Font-awesome with Bower ```bower install font-awesome```
8. Set sail ```sails lift```

#### Build errors compling less?
1. Update node to use grunt-contrib-less ```npm install grunt-contrib-less --save-dev```
2. Add the following line to the Gruntfile.js if needs be ```grunt.loadNpmTasks('grunt-contrib-less');```

#### Run persistanly on server
1. ```sudo npm install -g forever```
2. From your app directory, start the server with forever: ```forever start app.js --prod```

#####Other things you'll likely want to do in production
1. Configure your app to run on port 80 (if not behind a proxy like nginx)
2. Put it in "production" mode so that all of your css/js gets bundled up (requires linker)

{% highlight javascript %}
config/local.js
// Local configuration
//
// Included in the .gitignore by default,
// this is where you include configuration overrides for your local system
// or for a production deployment.
//
// For example, to use port 80 on the local machine, override the `port` config
module.exports = {
    port: 80,
    environment: 'production',
    adapters: {
        mysql: {
            user: 'root',
            password: '12345'
        }
    }
}
{% endhighlight %}

