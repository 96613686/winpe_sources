# Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ReadDataInBackgroundThread

- ea: `0x7dcd0`
- end: `0x7ddf0`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::ReadDataInBackgroundThread`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x67bb0`
- `0x67bc0`
- `0x67bd0`
- `0x67be0`
- `0x67bf0`
- `0x67d70`
- `0x68150`
- `0x68170`
- `0x7cd60`
- `0x7cd80`
- `0x7dcd0`
- `0x7ddf0`
- `0x7e8c0`
- `0xa2740`
- `0xa2790`

## string_xrefs

- `0x7dd2b`: `CannotConnectToTaskSchedulerService`
- `0x7dd45`: `CannotConnectToTaskSchedulerService`
- `0x7ddca`: `CannotConnectToTaskSchedulerService`
- `0x7ddb7`: `JobsServiceException`

## pseudocode

```c

```

## disassembly

```asm
0x7dcd0  ldarg.0
0x7dcd1  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::get_DataModel()
0x7dcd6  isinst   Microsoft.Windows.ManagementUI.CombinedControls.UITaskService
0x7dcdb  stloc.0
0x7dcdc  ldarg.0
0x7dcdd  ldloc.0
0x7dcde  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7dce3  ldloc.0
0x7dce4  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_User()
0x7dce9  ldloc.0
0x7dcea  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_Domain()
0x7dcef  ldloc.0
0x7dcf0  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EncryptedPassword()
0x7dcf5  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::CreateUITaskService(string computerName, string user, string domain, class [mscorlib]System.Security.SecureString encryptedPassword)
0x7dcfa  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::secondThreadTaskService
0x7dcff  ldarg.0
0x7dd00  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::get_IsShowHiddenTasks()
0x7dd05  stloc.1
0x7dd06  ldarg.0
0x7dd07  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::secondThreadTaskService
0x7dd0c  ldloc.0
0x7dd0d  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x7dd12  ldloc.0
0x7dd13  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_User()
0x7dd18  ldloc.0
0x7dd19  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_Domain()
0x7dd1e  ldloc.0
0x7dd1f  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EncryptedPassword()
0x7dd24  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ConnectToMachine(string computerName, string user, string domain, class [mscorlib]System.Security.SecureString encryptedPassword)
0x7dd29  brtrue.s loc_7DD3B
0x7dd2b  ldstr    aCannotconnectt// "CannotConnectToTaskSchedulerService"
0x7dd30  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7dd35  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7dd3a  throw
0x7dd3b  ldloc.0
0x7dd3c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_RootTaskFolder()
0x7dd41  stloc.2
0x7dd42  ldloc.2
0x7dd43  brtrue.s loc_7DD55
0x7dd45  ldstr    aCannotconnectt// "CannotConnectToTaskSchedulerService"
0x7dd4a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7dd4f  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7dd54  throw
0x7dd55  ldarg.0
0x7dd56  ldc.i4.0
0x7dd57  ldnull
0x7dd58  newobj   instance void TaskHomePageUpdateUiArgs::.ctor(valuetype UiUpdateTypeEnum uiUpdateType, object data)
0x7dd5d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::UpdateUi(class TaskHomePageUpdateUiArgs uiUpdateArgs)
0x7dd62  ldarg.0
0x7dd63  ldarg.2
0x7dd64  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::DeterminePastTaskActivityFromTaskSchedulerEvents(class [System]System.ComponentModel.DoWorkEventArgs e)
0x7dd69  ldarg.0
0x7dd6a  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7dd6f  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x7dd74  brfalse.s loc_7DD7D
0x7dd76  ldarg.2
0x7dd77  ldc.i4.1
0x7dd78  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x7dd7d  ldarg.0
0x7dd7e  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksList
0x7dd83  brfalse.s loc_7DD90
0x7dd85  ldarg.0
0x7dd86  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksList
0x7dd8b  callvirt instance void [mscorlib]System.Collections.ArrayList::Clear()
0x7dd90  ldarg.0
0x7dd91  ldarg.0
0x7dd92  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::secondThreadTaskService
0x7dd97  ldarg.0
0x7dd98  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Windows.ManagementUI.CombinedControls.UITask> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::allTasksDictionary
0x7dd9d  ldloc.1
0x7dd9e  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetSortedActiveTaskList(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Windows.ManagementUI.CombinedControls.UITask> allTasksCache, bool includeHiddenTasks)
0x7dda3  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksList
0x7dda8  ldarg.0
0x7dda9  ldnull
0x7ddaa  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Windows.ManagementUI.CombinedControls.UITask> Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::allTasksDictionary
0x7ddaf  ldarg.0
0x7ddb0  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::activeTasksList
0x7ddb5  brtrue.s loc_7DDC7
0x7ddb7  ldstr    aJobsserviceexc// "JobsServiceException"
0x7ddbc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ddc1  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7ddc6  throw
0x7ddc7  leave.s  loc_7DDDA
0x7ddc9  pop
0x7ddca  ldstr    aCannotconnectt// "CannotConnectToTaskSchedulerService"
0x7ddcf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7ddd4  newobj   instance void ReadingDataFailedException::.ctor(string errorMsg)
0x7ddd9  throw
0x7ddda  ldarg.0
0x7dddb  ldfld    class [System]System.ComponentModel.BackgroundWorker Microsoft.Windows.ManagementUI.CombinedControls.TaskHomeMainControl::dataReaderThread
0x7dde0  callvirt instance bool [System]System.ComponentModel.BackgroundWorker::get_CancellationPending()
0x7dde5  brfalse.s loc_7DDEF
0x7dde7  ldarg.2
0x7dde8  ldc.i4.1
0x7dde9  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x7ddee  ret
0x7ddef  ret
```
