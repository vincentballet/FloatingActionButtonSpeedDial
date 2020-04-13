# Change Log
## [3.1.1] - 2019-09-10
- Fix #11: Re-enabling FAB size
- Revert `com.google.android.material` to `1.0.0` (version `1.1.0-beta01` can still be used, just specify this version explicitly on your build.gradle file).

## [3.1.0] - 2019-09-10
- fixed #113: Main FAB opened image is not centered when using Theme.MaterialComponents
- fixed #101: Add ability to Disable Main Fab
- API changes:
    - fixed #111: added option to tint Main FAB icon (`setMainFabClosedIconColor()` and `setMainFabOpenedIconColor()`)
- migrated Sample project to Kotlin

## [3.0.0] - 2019-07-27
- fixed #92: Migrate to AndroidX
- fixed #100: Use unique view IDs
- fixed #109: Added resource ID for main FAB
- updated gradle and Android gradle plugin

## [2.0.1] - 2018-09-28
- fixed #95: support 28 workaround does not work on minified release apk

## [2.0.0] - 2018-09-23
- updated support library to v28.0.0
- workaround for https://issuetracker.google.com/issues/111316656 <- **PLEASE STAR THIS ISSUE**
- fixed #79: Does not change label text language when app language is changed dynamically
- fixed #88: Speed Dial should not open if empty
- API changes:
    - added support to String resources for labels
    - `SpeedDialActionItem.getLabel()` now requires a `Context`
    - added `SpeedDialActionItem.Builder()` constructor that accepts a `SpeedDialActionItem` to be used for default values (useful to modify an existing Action Item without replacing it completely)
    - added `SpeedDialActionItem.createFabWithLabelView()`
    - all the `SpeedDialView` add and replace methods now return an instance of the `FabWithLabelView` they create  (useful to modify an existing Action Item without replacing it completely)
    - added `FabWithLabelView.getSpeedDialActionItemBuilder()`  (useful to modify an existing Action Item without replacing it completely)
    
## [1.0.2] - 2018-06-30
- fixed #65: Main FAB not centered when using RTL
- fixed #71: Animation feels slower than Google Inbox
- fixed #72: FAB vertical padding should be 16dp instead of 18dp

## [1.0.1] - 2018-06-15
- fixed #62: Click between Label and FAB handled as a dismiss action
- fixed #60: Label transparent background not being applied

## [1.0.0] - 2018-06-03
- first stable release (no changes from 1.0-alpha06)

## [1.0-alpha06] - 2018-05-12
- updated gradle plugin to 3.1.2
- several API changes:
    - added `sdOverlayLayout` attribute
    - added `SpeedDialView.setUseReverseAnimationOnClose()` and `SpeedDialView.getUseReverseAnimationOnClose()` (thanks to @jahirfiquitiva)
    - renamed `SpeedDialView.getMainFabCloseRotateAngle()` to `SpeedDialView.getMainFabAnimationRotateAngle()`
    - renamed `SpeedDialView.setMainFabCloseRotateAngle()` to `SpeedDialView.setMainFabAnimationRotateAngle()`
    - renamed `SpeedDialView.setMainFabOpenDrawable()` to `SpeedDialView.setMainFabClosedDrawable()`
    - renamed `SpeedDialView.setMainFabCloseDrawable()` to `SpeedDialView.setMainFabOpenedDrawable()`
    - renamed `SpeedDialView.getMainFabOpenBackgroundColor()` to `SpeedDialView.getMainFabClosedBackgroundColor()`
    - renamed `SpeedDialView.setMainFabOpenBackgroundColor()` to `SpeedDialView.setMainFabClosedBackgroundColor()`
    - renamed `SpeedDialView.getMainFabCloseBackgroundColor()` to `SpeedDialView.getMainFabOpenedBackgroundColor()`
    - renamed `SpeedDialView.setMainFabCloseBackgroundColor()` to `SpeedDialView.setMainFabOpenedBackgroundColor()`
    - renamed `sdMainFabOpenSrc` to `sdMainFabClosedSrc`
    - renamed `sdMainFabOpenBackgroundColor` to `sdMainFabClosedBackgroundColor`
    - renamed `sdMainFabCloseSrc` to `sdMainFabOpenedSrc`
    - renamed `sdMainFabCloseBackgroundColor` to `sdMainFabOpenedBackgroundColor`
    - renamed `sdMainFabCloseRotateAngle` to `sdMainFabAnimationRotateAngle`

## [1.0-alpha05] - 2018-04-15
- added Menu Resource support (no color customization possible)
- `Drawable`s are not parcelables so is not possible to restore them when the view is recreated 
  for example after an orientation change. If possible always use the `DrawableRes`.
- fixed Expansion mode and rotate angle not persisted on orientation change
- fixed inverted behavior for `SpeedDialView.setMainFabClosedBackgroundColor` 
  and `SpeedDialView.setMainFabOpenedBackgroundColor`
- added `SpeedDialView.getActionItems()`
- added `SpeedDialView.getMainFab()`
- `SpeedDialView.OnChangeListener.onMainActionSelected()` now returns true to keep the Speed Dial open, false to close it
- optional no animation for open/close/toggle

## [1.0-alpha04] - 2018-04-14
- android support library 27.1.1
- lowered minSdk from 15 to 14
- several API changes:
    - renamed `FabWithLabelView.setOptionFabSelectedListener()` to `FabWithLabelView.setOnActionSelectedListener()`
    - renamed `FabWithLabelView.isLabelEnable()` to `FabWithLabelView.isLabelEnabled()`
    - added `SpeedDialActionItem.Builder(@IdRes int id, @Nullable Drawable d)`
    - added `SpeedDialView.setOnChangeListener(OnChangeListener l)`
    - removed `SpeedDialView.setMainFabOnClickListener(OnClickListener l)`
    - renamed `OnOptionFabSelectedListener` to `OnActionSelectedListener`
    - renamed `SpeedDialView.setOptionFabSelectedListener()` to `SpeedDialView.setOnActionSelectedListener()`
    - renamed `SpeedDialView.addAllFabOptionItem()` to `SpeedDialView.addAllActionItems()`
    - renamed `SpeedDialView.addFabOptionItem()` to `SpeedDialView.addActionItem()`
    - renamed `SpeedDialView.replaceFabOptionItem()` to `SpeedDialView.replaceActionItem()`
    - renamed `SpeedDialView.removeFabOptionItemById()` to `SpeedDialView.removeActionItemById()`
    - renamed `SpeedDialView.removeFabOptionItem()` to `SpeedDialView.removeActionItem()`
    - renamed `SpeedDialView.isFabMenuOpen()` to `SpeedDialView.isOpen()`
    - renamed `SpeedDialView.closeOptionsMenu()` to `SpeedDialView.close()`
    - renamed `SpeedDialView.openOptionsMenu()` to `SpeedDialView.open()`
    - renamed `SpeedDialView.toggleOptionsMenu()` to `SpeedDialView.toggle()`
    - removed attributes `android:src`
    - renamed attributes `srcCompat` to `sdMainFabClosedSrc`
    - renamed attributes `sdFabOpenedSrc` to `sdMainFabOpenedSrc`
    - removed attributes `sdFabRotateOnToggle`
    - added attributes `sdMainFabAnimationRotateAngle`
 - minor fixes

## [1.0-alpha03] - 2018-04-02
- fixed #4: FAB icons rotate only once
- renamed attribute close_src to sdFabOpenedSrc
- added attributes `sdFabRotateOnToggle` and `sdExpansionMode`
- fixed various minor UI issues

## [1.0-alpha02] - 2018-04-01
- first public release
