# Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::RegisterTask

- ea: `0x4a700`
- end: `0x4a772`
- name: `Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::RegisterTask`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x49110`
- `0x4a700`
- `0x4ae50`
- `0x4aeb0`
- `0x62a40`
- `0x62ad0`

## string_xrefs

- `0x4a70c`: `directory`
- `0x4a717`: `taskXmlContent`

## pseudocode

```c

```

## disassembly

```asm
0x4a700  ldarg.1
0x4a701  ldstr    aName// "name"
0x4a706  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x4a70b  ldarg.2
0x4a70c  ldstr    aDirectory_1// "directory"
0x4a711  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x4a716  ldarg.3
0x4a717  ldstr    aTaskxmlcontent// "taskXmlContent"
0x4a71c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x4a721  ldarg.0
0x4a722  call     instance class WindowsTaskSchedulerInterop.TaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetTaskScheduler()
0x4a727  stloc.0
0x4a728  ldloc.0
0x4a729  ldsfld   object [mscorlib]System.Type::Missing
0x4a72e  ldsfld   object [mscorlib]System.Type::Missing
0x4a733  ldsfld   object [mscorlib]System.Type::Missing
0x4a738  ldsfld   object [mscorlib]System.Type::Missing
0x4a73d  callvirt instance void WindowsTaskSchedulerInterop.ITaskService::Connect([in] [opt] [hasfieldmarshal] object serverName, [in] [opt] [hasfieldmarshal] object user, [in] [opt] [hasfieldmarshal] object domain, [in] [opt] [hasfieldmarshal] object password)
0x4a742  ldarg.0
0x4a743  ldloc.0
0x4a744  ldarg.2
0x4a745  ldc.i4.1
0x4a746  call     instance class WindowsTaskSchedulerInterop.ITaskFolder Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetFolder(class WindowsTaskSchedulerInterop.TaskScheduler taskScheduler, string directory, [opt] bool createIfNotExist)
0x4a74b  ldarg.s  4
0x4a74d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a752  brfalse.s loc_4A760
0x4a754  ldsfld   unsigned int8[] Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::SystemSid
0x4a759  call     string Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::GetAccountName(unsigned int8[] sid)
0x4a75e  br.s     loc_4A762
0x4a760  ldarg.s  4
0x4a762  stloc.1
0x4a763  ldarg.1
0x4a764  ldarg.3
0x4a765  ldc.i4.6
0x4a766  ldloc.1
0x4a767  ldnull
0x4a768  ldarg.s  5
0x4a76a  ldnull
0x4a76b  callvirt instance class WindowsTaskSchedulerInterop.IRegisteredTask WindowsTaskSchedulerInterop.ITaskFolder::RegisterTask([hasfieldmarshal] string, [in] [hasfieldmarshal] string Path, [in] [hasfieldmarshal] int32 XmlText, [in] object flags, [in] [hasfieldmarshal] object UserId, [in] [hasfieldmarshal] valuetype WindowsTaskSchedulerInterop._TASK_LOGON_TYPE password, [in] object LogonType)
0x4a770  pop
0x4a771  ret
```
