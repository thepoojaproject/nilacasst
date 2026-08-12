# NilamCast APK — FINAL

This is the final GitHub-ready Android project for the NilamCast IPTV app.

## Login
- Login: `Neelam`
- Password: `Neelam143`

## Footer
**Made with ❤️ for Neelam**

## Final build fix
The previous GitHub build failed with:

`error: invalid source release: 21`

That means the Android build was asking Java to compile for Java 21 while GitHub was using an older JDK.

This final version explicitly installs **Temurin JDK 21** before the Android build.

It also:
- uses `capacitor.config.json` (no TypeScript required)
- uses `npm install` instead of `npm ci`
- does not include a stale `package-lock.json`
- builds `app-debug.apk`
- uploads the APK as a GitHub Actions artifact

## GitHub
Upload the contents of this project to your repository, replacing the old workflow/files.

Then:
**Actions → Build NilamCast APK → Run workflow**

After the build succeeds:
**Build NilamCast APK → Artifacts → NilamCast-APK**


## Latest GitHub Actions fix
The `setup-java` step no longer uses `cache: gradle` before the Android project exists.
It now uses `actions/setup-java@v5` with Temurin JDK 21, then creates the Android project with Capacitor, syncs it, and builds the APK.


## Mobile update
The NilamCast page is now mobile responsive and includes `www/logo.png`. The video, search box, channel list, login form, and buttons scale to phone screens.


## Advanced Netflix-style UI
- Netflix-inspired dark mobile-first interface
- Hero banner with Watch Now / More Info
- Category navigation: Home, News, Sports, Entertainment, Music
- Live channel cards with favorites
- Search overlay
- My List using localStorage
- Settings modal and logout
- Responsive player and bottom navigation
- HLS playback remains supported
