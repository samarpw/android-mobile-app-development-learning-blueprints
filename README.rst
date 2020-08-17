Android Mobile App Development Learning Guide
=======

The programming language for mobile development on Android is very
simple – Java. Google is now actively promoting Kotlin as a language
that can replace Java. Applications are also written in C++.

The creation of a simple application consists of several stages:

-  project in Android Studio;
-  creating a user interface;
-  adding activities, navigation and actions;
-  test drive the application in the emulator.

Required tools
~~~~~~~~~~~~~~

The first step is to install the `Android Studio`_ program . This is the
official development environment (IDE) for Android and runs on Windows,
macOS and Linux. Although you can use other environments besides Android
Studio when developing programs for Android.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-7.png?w=1024
   :alt: 
   :figclass: wp-image-83

If the **Android SDK** and other components are not installed on your
computer ,  **Android Studio** will automatically download them. The
Android SDK is a programming environment that includes libraries,
executables, scripts, documentation, etc.

**The Android SDK** compiles

.. _Android Studio: https://developer.android.com/studio/?roistat_visit=12247356

the code along with any data and resources into an\ * .apk* file. It
contains everything you need to install an application on an Android
device.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-6.png?w=800
   :alt: 
   :figclass: wp-image-82

It is useful to install an *Android* emulator as well in order to run
and test applications. The emulator comes bundled with  *Android
Studio* .

.. figure:: https://opendr.files.wordpress.com/2020/08/image-5.png?w=800
   :alt:

When all the tools are installed, you can create your first project. But
first, you need to understand the basic concepts.

What does an 
Android application consist of ?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

An Android application has four components. Each component is an entry
point through which a system or user can access.

#. `Activity`_\ ** (activity)** – the elements of an interactive user
   interface. 
   *One activity engages another and passes information about what the
   user intends to do through the Intent class. Activities are like web
   pages, and intents are like links between them. Application launch is
   the Main activity.* 
#. `Service`_\ ** (service,)** – a universal entry point to maintain the
   application in the background. 
   *This component performs long running operations or work for remote
   processes without a visual interface.*
#. `A broadcast receiver`_ broadcasts intents from an application to
   multiple participants.
#. `A`_\ content provider manages a common set of application data from
   the file system, SQLite database, internet, or other storage.

Now let’s try to make our own application for Android.

Building an Android app 
in Android Studio
~~~~~~~~~~~~~~~~~~~~~~~~

**Step 1**
^^^^^^^^^^

.. _Activity: https://developer.android.com/guide/components/activities.html?roistat_visit=12247356
.. _Service: https://developer.android.com/guide/components/services.html?roistat_visit=12247356
.. _A broadcast receiver: https://developer.android.com/reference/android/content/BroadcastReceiver.html?roistat_visit=12247356
.. _A: https://developer.android.com/guide/topics/providers/content-providers.html?roistat_visit=12247356

Select the application name, company domain, project path and package
name. We indicate whether to enable support for the optional programming
languages ​​C ++ and Kotlin.

**Step 2**
^^^^^^^^^^

We set one or more target platforms for the build. It uses SDK and AVD,
Android virtual device manager. The tool allows you to install packages
into the SDK that support multiple Android OS versions and multiple API
(Application Programming Interface) levels.

--------------

**reference**

   The lower the Android version, the more devices on which the
   application will run. The higher the version, the richer the API
   functionality.

--------------

**Step 3**
^^^^^^^^^^

Select the main activity that will be launched when you click on the
application icon, and give it a name.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-4.png?w=916
   :alt: 
   :figclass: wp-image-80

**Step 4**
^^^^^^^^^^

After a few minutes of building, Android Studio opens the IDE
interface. There are three main points here.

If you select Android view from the drop-down menu, you will see the
project files. For example, our main activity is named **app> java>
en.appbox.\ appbox\ app> FullscreenActivity** . When creating the
project, we specified a full-screen activity instead of
the *Main* activity.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-3.png?w=719
   :alt: 
   :figclass: wp-image-79

Next, you can see the file **app> res> layout>
activity_fullscreen.xml** . This is an XML layout file for the UI of our
main activity.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-2.png?w=727
   :alt: 
   :figclass: wp-image-78

Finally, the third important file **app> manifests>
AndroidManifest.xml** describes the fundamental characteristics of the
application and defines all its components.

**Manifest content**
^^^^^^^^^^^^^^^^^^^^
``<?xml version="1.0" encoding="utf-8"?> <manifest xmlns:android="http://schemas.android.com/apk/res/android"     package="en.appbox.appboxapp">     <application         android:allowBackup="true"         android:icon="@mipmap/ic_launcher"         android:label="@string/app_name"         android:roundIcon="@mipmap/ic_launcher_round"         android:supportsRtl="true"         android:theme="@style/AppTheme">         <activity             android:name=".FullscreenActivity"             android:configChanges="orientation|keyboardHidden|screenSize"             android:label="@string/app_name"             android:theme="@style/FullscreenTheme">             <intent-filter>                 <action android:name="android.intent.action.MAIN" />                 <category android:name="android.intent.category.LAUNCHER" />             </intent-filter>         </activity>     </application> </manifest>``

Run on a real device
~~~~~~~~~~~~~~~~~~~~

The application we created is one activity that runs in full screen mode
and has no graphical elements.

We run it on an Android device or in an emulator.

Smartphone or tablet to connect it to the USB-debugging mode, which is
activated in the  **Settings developer**  in the menu *settings* .

To run the emulator in Android Studio click the button **Run** in the
menu *Run* (the Shift + the F10). We select the appropriate device and
OS version, portrait or landscape (landscape) orientation.

.. figure:: https://opendr.files.wordpress.com/2020/08/image-1.png?w=1016
   :alt: Android Studio will install the emulator and launch it.
   :figclass: wp-image-77

   Android Studio will install the emulator and launch it.

Building a simple user interface
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The user interface of an Android application is built through a
hierarchy of **layouts**\ (layouts, ViewGroup objects)
and  **widgets** (View objects). Layouts control the layout of child
widgets on the screen. The widgets themselves are directly UI
components: buttons, text fields on the screen, etc.

The activity interface is created in Android Studio in the Layout Editor
and is stored mostly in XML files.

#. Open the file **app> res> layout> activity_fullscreen.xml** .
#. Add widgets to the screen from the Palette by dragging the mouse.
#. For example, let’s take a text field (PlainText). This is an EditText
   widget where the user can enter text.
#. Add buttons and other necessary elements.

.. figure:: https://opendr.files.wordpress.com/2020/08/image.png?w=848
   :alt: You can also drag buttons and other elements onto the screen.
   :figclass: wp-image-76

   You can also drag buttons and other elements onto the screen.

Adding actions, activities and navigation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Let’s say we created an activity with a text box and a Submit
button. After that, you need to write what exactly will happen when you
click the “Send” button.

#. Go to the code **app> java> FullscreenActivity** .
#. Add the *SendMessage ()* method to
   the **FullscreenActivity** class so that when the button is clicked,
   this method is called.
#. We create intents (Intent class) for moving from one activity to
   another, new activities, navigation and everything else that is
   necessary for the application.

And, of course, we start dreaming of how to monetize the application.

General rules 
for Android applications
~~~~~~~~~~~~~~~~~~~~~~~~

The Android application lives in its own sandbox, which obeys the Linux
security rules:

#. Each application is a separate user on a multiuser Linux system.
#. By default, the system assigns each application a unique user ID that
   is unknown to the application; all files are accessible only to this
   user ID.
#. All processes have their own virtual machine (VM), so that the
   executable code is isolated from other applications.
#. By default, each application starts its own Linux process.

There are exceptions to the rules:

#. It is possible for two applications to have a common user ID so that
   they can share files with each other.
#. The application can request permission to access the user’s contacts,
   SMS, drive content, information from the camera and other data.
