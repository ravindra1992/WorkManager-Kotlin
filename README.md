# WorkManager-Kotlin
Work Manager -Kotlin 

WorkManager is a task scheduler used to perform backgroudn async operation with a guarantee to be executed. 
Its is a part of Android JetPack.

Gradle Dependency:

ext {
    work_manager_version = '1.0.0'
}

implementation "android.arch.work:work-runtime-ktx:$work_manager_version"

Steps:
1-Create Worker
2-Set Constraints
3-Check , is it periodic?
3a)- Yes- Create Perodic work req
3b)- No- Create One time work req
4-Scehdule to work manager


Why WorkManager?- 

Before this we have firebase job dispatcher/Alarm mamager/Job scheduler but the issue were:

Job Scehduler- Availabe only on API >=21
Firebase Job dispatcher- for backward compatibility

To overcome these issue we have work manager.It will automaticlly choose the best mehtod for you task. 
You dont nend to write logic for it.

When to use WorkManager?

Handles compatibility with different OS versions
Follows system health best practices
Supports asynchronous one-off and periodic tasks
Supports chained tasks with input/output
Lets you set constraints on when the task runs
Periodically syncing local data with the network
Uploading logs
Guarantees task execution, even if the app or device restarts


WorkManager Features:


i)- Fully backward compatibility .so you dont need to check the Android version.
ii)-Runs with or without Google play services.
iii)-Task can be chanied as well ie one task is finished it can start another.
iv)- It provide guarantee execution.

WorkManager Classes:

Worker- The class where we will put the work that needs to be done.
WorkRequest-It defines an individual task .
WorkManager- This class used to enqueue the work requests.
WorkInfo- This class contains information about the works. The LiveData holds the workinfo and by observing it we can determine 
the work info.

Constraints:


A worker’s constraints specifies the requirements that need to be met before be executed. 
These constraints can be related to network, battery or storage:

getRequiredNetworkType()
requiresBatteryNotLow()
requiresCharging()
requiresDeviceIdle()
requiresStorageNotLow()
  












