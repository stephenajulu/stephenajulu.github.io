---
published: false
---
## Invest in Yourself


<!-- wp:paragraph -->
<p> Hey guys, how are you? I am back again with another post. You can also check out my previous post on "<a href="https://ajulusthoughts.wordpress.com/2018/12/11/using-android-as-a-hacking-platform-no-root/">Using Android as a Hacking Platform: No Root</a>". It has hit! With more than 23 hits each day since i posted it. So far it has gained 1,278 views.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p> Now it’s possible to open your Linux command prompt on your Android  phone to get some things done. Usually installing Linux on Android phones needs rooting your device. But now.....</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"dropCap":true} -->
<p class="has-drop-cap">With just a few taps, an Android phone can be weaponized into a covert  hacking device capable of running tools such as Nmap, Nikto, and Netcat — all without rooting the device. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a rel="noreferrer noopener" href="https://github.com/CypherpunkArmory/UserLAnd" target="_blank">UserLAnd</a>, created by <a rel="noreferrer noopener" href="https://userland.tech/" target="_blank">UserLAnd Technologies</a>,  is a completely free Android app that makes installing Linux  distributions quick and effortless, without any rooting. With this, it’s  possible to run an <a rel="noreferrer noopener" href="https://wiki.debian.org/Arm64Port" target="_blank">ARM64 Debian</a> operating  system alongside the current Android OS. Sometimes referred to as  “AARCH64,” this ARM architecture is the same used by the <a rel="noreferrer noopener" href="https://www.offensive-security.com/kali-linux-arm-images/" target="_blank">Kali Linux Raspberry Pi ARM images</a>,  which makes it easy to import Kali’s tool repository. And best of all,  the UserLAnd team recently added a dedicated Kali filesystem so  importing repositories won’t be necessary for all users.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1886,"width":301,"height":556} -->
<figure class="wp-block-image is-resized"><img src="https://ajulusthoughts.files.wordpress.com/2019/06/phone-feature.d3014400.gif" alt="" class="wp-image-1886" width="301" height="556" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>All of the created filesystems are easily disposable. While many Kali
 tools work without issues, UserLAnd is still a new project and may 
cause some tools (<a rel="noreferrer noopener" href="https://github.com/CypherpunkArmory/UserLAnd/issues/385" target="_blank">like Nmap</a>)
 to break or fail when executing certain commands. It’s worth 
mentioning, these issues will likely be resolved in the near future.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>For the technically inclined, UserLAnd <a rel="noreferrer noopener" href="https://www.youtube.com/watch?v=PdVmfAD2T54" target="_blank">utilizes</a> custom scripts and executables that allow it to create the Debian and Ubuntu filesystems. One example of this is <a rel="noreferrer noopener" href="https://proot-me.github.io/" target="_blank">PRoot</a>, an <a rel="noreferrer noopener" href="https://github.com/proot-me/PRoot" target="_blank">open-source software</a> that implements functionalities similar to <a rel="noreferrer noopener" href="https://www.computerhope.com/jargon/c/chroot.htm" target="_blank">chroot</a>. PRoot allows you to execute programs with an alternative root directory, no root needed. Normally, a <a rel="noreferrer noopener" href="https://unix.stackexchange.com/questions/87625/what-is-difference-between-user-space-and-kernel-space" target="_blank">user-space</a> application will communicate directly with the Kernel through <a rel="noreferrer noopener" href="https://en.wikipedia.org/wiki/System_call" target="_blank">system calls</a>.  With UserLAnd, PRoot is running in the background, interpreting these  system calls, and it will perform and manipulate them when necessary to  emulate users and permissions in the filesystem.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We’ll start by installing an SSH client, which will be the primary  app for interacting with the Debian OS. Then, I’ll walk through some OS  setup tips and importing the Kali Linux repository to really turn  Android into a hacking device. As some readers may know, Kali Linux is  based on the Debian operating system, so importing their repository  won’t cause anything to break or become unreliable.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1887} -->
<figure class="wp-block-image"><img src="https://ajulusthoughts.files.wordpress.com/2019/06/phone-feature-horizontal.be4009ad.gif" alt="" class="wp-image-1887" /></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Step 1: Install the ConnectBot App (Optional)</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>UserLAnd recently added a built-in SSH functionality, so this step is
 no longer required. However, third-party SSH clients can still be used 
if preferred.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://connectbot.org/" rel="noreferrer noopener" target="_blank">ConnectBot</a>&nbsp;is an&nbsp;<a href="https://github.com/connectbot" rel="noreferrer noopener" target="_blank">open-source</a>&nbsp;SSH
 client designed for Android smartphones, which allows you to securely 
connect with SSH servers. This will be the primary way of interacting 
with the new UserLAnd Debian operating system. If you don’t use or have 
access to Google Play, ConnectBot is available via the&nbsp;<a href="https://f-droid.org/" rel="noreferrer noopener" target="_blank">F-Droid repository</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li><strong>Play Store Link:&nbsp;<a href="https://play.google.com/store/apps/details?id=org.connectbot" rel="noreferrer noopener" target="_blank">ConnectBot</a>&nbsp;(free)</strong></li><li><strong>F-Droid Link:&nbsp;<a href="https://f-droid.org/packages/org.connectbot/" rel="noreferrer noopener" target="_blank">ConnectBot</a>&nbsp;(free)</strong></li></ul>
<!-- /wp:list -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://i2.wp.com/img.wonderhowto.com/img/75/02/63684544346074/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=490%2C186&amp;ssl=1" alt="" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://play.google.com/store/apps/details?id=com.sonelli.juicessh&amp;hl=en_US" rel="noreferrer noopener" target="_blank">JuiceSSH</a>&nbsp;is
 also a very good option to use instead of ConnectBot since it has more 
features, so you can use that if you’d rather. ConnectBot is more 
regularly updated and easier for beginners, so we went with that.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Step 2: Install the UserLAnd App</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>I’ve already covered what UserLAnd is and does above, so I won’t go 
over anything else in detail here. The important thing is that you 
install it, and you can do so using either Google Play or F-Droid.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li><strong>Play Store Link:&nbsp;<a rel="noreferrer noopener" href="https://play.google.com/store/apps/details?id=tech.ula" target="_blank">UserLAnd</a>&nbsp;(free)</strong></li><li><strong>F-Droid Link:&nbsp;<a rel="noreferrer noopener" href="https://f-droid.org/packages/tech.ula/" target="_blank">UserLAnd</a>&nbsp;(free)</strong></li></ul>
<!-- /wp:list -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://i0.wp.com/img.wonderhowto.com/img/59/80/63684544601996/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=546%2C210&amp;ssl=1" alt="" /></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Disclaimer: UserLAnd does have limitations. Without root access, 
Android’s Wi-Fi interface can’t be switched into monitor mode, so 
traditional&nbsp;Wi-Fi hacking tools&nbsp;like Aircrack-ng won’t work. However, 
there’s still a lot that can be done with UserLAnd, as you’ll see in 
future guides, and running Kali without rooting or wiping the Android OS
 is no easy achievement. So be sure to give the UserLAnd app a good 
rating on Google Play — the developers totally deserve some positive 
feedback.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Step 3: Create a New Filesystem</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>When the installation is complete, open UserLAnd, and view the “Apps”
 tab. Refresh the tab and wait a few minutes for the distributions to 
populate.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The Kali Linux OS has recently been added to the list of available 
distributions. Select “Kali” or “Debian” and the UserLAnd app will 
prompt for credentials. Create a username, password, and VNC password. 
The “Password” will allow access to the SSH server started when the 
filesystem is finished installing. The “VNC Password” won’t be used in 
this tutorial but is required to proceed with the installation.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"right"} -->
<div class="wp-block-image"><figure class="alignright"><img src="https://i0.wp.com/img.wonderhowto.com/img/83/85/63682308217661/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=256%2C441&amp;ssl=1" alt="" /></figure></div>
<!-- /wp:image -->

<!-- wp:image {"align":"right"} -->
<div class="wp-block-image"><figure class="alignright"><img src="https://i0.wp.com/img.wonderhowto.com/img/78/54/63684474970332/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=260%2C449&amp;ssl=1" alt="" /></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>UserLAnd&nbsp;<a href="https://img.wonderhowto.com/img/original/89/11/63676930363763/0/636769303637638911.jpg">will then download</a>&nbsp;the
 necessary executables and scripts from its GitHub repository that are 
used to create the filesystems. The time it takes to download and 
extract the required assets will vary based on the Android CPU and 
internet connection speed. The installation process took up to 20 
minutes to complete in some tests, so be patient.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In my first attempt, UserLAnd returned the following “<a href="https://github.com/CypherpunkArmory/UserLAnd/issues/369" rel="noreferrer noopener" target="_blank">Could not extract filesystem. Something went wrong</a>” error. Removing and reinstalling the UserLAnd application seemed to resolve the issue. If this error persists,&nbsp;<a href="https://github.com/CypherpunkArmory/UserLAnd/issues/" rel="noreferrer noopener" target="_blank">open a new GitHub issue</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Step 4: Interact with the Filesystem</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>When the installation is complete, head over to the “Sessions” tab, 
and select the newly created option. UserLAnd will automatically attempt
 to open ConnectBot and ask “Are you sure you want to continue 
connecting?” Tap “Yes,” and enter the password created in the previous 
step.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"right"} -->
<div class="wp-block-image"><figure class="alignright"><img src="https://i1.wp.com/img.wonderhowto.com/img/41/99/63684545118465/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=250%2C431&amp;ssl=1" alt="" /></figure></div>
<!-- /wp:image -->

<!-- wp:image {"align":"right","linkDestination":"custom"} -->
<div class="wp-block-image"><figure class="alignright"><a href="https://i2.wp.com/img.wonderhowto.com/img/original/26/55/63684545108512/0/636845451085122655.jpg?ssl=1" target="_blank" rel="noreferrer noopener"><img src="https://i2.wp.com/img.wonderhowto.com/img/26/55/63684545108512/0/android-for-hackers-turn-android-phone-into-hacking-device-without-root.w1456.jpg?resize=250%2C431&amp;ssl=1" alt="" /></a></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>At this point, syncing a&nbsp;Bluetooth keyboard&nbsp;to the phone will make 
setting up the OS easier, but isn’t required. If you don’t use a 
Bluetooth keyboard, I recommend installing&nbsp;<a rel="noreferrer noopener" href="https://play.google.com/store/apps/details?id=org.pocketworkstation.pckeyboard" target="_blank">Hacker’s Keyboard</a>&nbsp;from the Play Store, and you’ll see why as we continue.</p>
<!-- /wp:paragraph -->
