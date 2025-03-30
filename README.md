# CheatSheet-For-android
android recources

for spinner or loader
xml-
<!-- Progress Bar (Spinner) -->
    <ProgressBar
        android:id="@+id/profileLoader"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:visibility="gone" />
kt-
 profileLoader.visibility = View.VISIBLE  // Show loader
profileContent.visibility = View.GONE  // Hide content
normal----
// Delay to show loader for 1-2 seconds
//                Handler(Looper.getMainLooper()).postDelayed({
//                    profileLoader.visibility = View.GONE  // Hide loader
//                    profileContent.visibility = View.VISIBLE  // Show content
//                }, 1500) // 1.5 seconds
//            }
annimated----
 // Animate Loader Disappearance & Profile Content Appearance
                profileLoader.animate()
                    .alpha(0f) // Fade out loader
                    .setDuration(1000)
                    .withEndAction {
                        profileLoader.visibility = View.GONE

                        profileContent.alpha = 0f
                        profileContent.visibility = View.VISIBLE
                        profileContent.animate()
                            .alpha(1f) // Fade in profile content
                            .setDuration(1000)
                            .start()
                    }.start() // 1.5 seconds
            }
profileLoader.visibility = View.GONE  // Hide loader in case of error
                profileContent.visibility = View.VISIBLE  // Show content
            


