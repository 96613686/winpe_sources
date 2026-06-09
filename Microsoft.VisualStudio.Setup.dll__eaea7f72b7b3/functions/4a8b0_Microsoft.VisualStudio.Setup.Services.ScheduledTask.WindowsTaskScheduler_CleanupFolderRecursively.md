# Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::CleanupFolderRecursively

- ea: `0x4a8b0`
- end: `0x4a9a7`
- name: `Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::CleanupFolderRecursively`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x4a380`
- `0x4a8b0`

## callees

- `0x4a8b0`
- `0x627c0`
- `0x62820`
- `0x629b0`
- `0x629e0`
- `0x62a00`
- `0x62a20`
- `0x62a30`
- `0x62a80`

## string_xrefs

- `0x4a8ef`: `Failed to delete task {0}: {1}`
- `0x4a96a`: `Failed to delete task folder {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4a8b0  ldarg.1
0x4a8b1  brtrue.s loc_4A8B4
0x4a8b3  ret
0x4a8b4  ldarg.1
0x4a8b5  ldc.i4.1
0x4a8b6  callvirt instance class WindowsTaskSchedulerInterop.IRegisteredTaskCollection WindowsTaskSchedulerInterop.ITaskFolder::GetTasks([hasfieldmarshal] int32)
0x4a8bb  callvirt instance class [mscorlib]System.Collections.IEnumerator WindowsTaskSchedulerInterop.IRegisteredTaskCollection::GetEnumerator()
0x4a8c0  stloc.0
0x4a8c1  br.s     loc_4A909
0x4a8c3  ldloc.0
0x4a8c4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a8c9  isinst   WindowsTaskSchedulerInterop.IRegisteredTask
0x4a8ce  stloc.1
0x4a8cf  ldloc.1
0x4a8d0  brfalse.s loc_4A909
0x4a8d2  nop
0x4a8d3  ldarg.1
0x4a8d4  ldloc.1
0x4a8d5  callvirt instance string WindowsTaskSchedulerInterop.IRegisteredTask::get_Name()
0x4a8da  ldc.i4.0
0x4a8db  callvirt instance void WindowsTaskSchedulerInterop.ITaskFolder::DeleteTask([in] [hasfieldmarshal] string Name, [in] int32 flags)
0x4a8e0  leave.s  loc_4A909
0x4a8e2  stloc.2
0x4a8e3  ldarg.0
0x4a8e4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::logger
0x4a8e9  dup
0x4a8ea  brtrue.s loc_4A8EF
0x4a8ec  pop
0x4a8ed  br.s     loc_4A907
0x4a8ef  ldstr    aFailedToDelete_11// "Failed to delete task {0}: {1}"
0x4a8f4  ldc.i4.2
0x4a8f5  newarr   [mscorlib]System.Object
0x4a8fa  dup
0x4a8fb  ldc.i4.0
0x4a8fc  ldloc.1
0x4a8fd  stelem.ref
0x4a8fe  dup
0x4a8ff  ldc.i4.1
0x4a900  ldloc.2
0x4a901  stelem.ref
0x4a902  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x4a907  leave.s  loc_4A909
0x4a909  ldloc.0
0x4a90a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a90f  brtrue.s loc_4A8C3
0x4a911  leave.s  loc_4A924
0x4a913  ldloc.0
0x4a914  isinst   [mscorlib]System.IDisposable
0x4a919  stloc.3
0x4a91a  ldloc.3
0x4a91b  brfalse.s loc_4A923
0x4a91d  ldloc.3
0x4a91e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a923  endfinally
0x4a924  ldarg.1
0x4a925  ldc.i4.0
0x4a926  callvirt instance class WindowsTaskSchedulerInterop.ITaskFolderCollection WindowsTaskSchedulerInterop.ITaskFolder::GetFolders([hasfieldmarshal] int32)
0x4a92b  callvirt instance class [mscorlib]System.Collections.IEnumerator WindowsTaskSchedulerInterop.ITaskFolderCollection::GetEnumerator()
0x4a930  stloc.0
0x4a931  br.s     loc_4A98B
0x4a933  ldloc.0
0x4a934  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a939  isinst   WindowsTaskSchedulerInterop.ITaskFolder
0x4a93e  stloc.s  4
0x4a940  ldloc.s  4
0x4a942  brfalse.s loc_4A98B
0x4a944  ldarg.0
0x4a945  ldloc.s  4
0x4a947  call     instance void Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::CleanupFolderRecursively(class WindowsTaskSchedulerInterop.ITaskFolder folder)
0x4a94c  ldarg.1
0x4a94d  ldloc.s  4
0x4a94f  callvirt instance string WindowsTaskSchedulerInterop.ITaskFolder::get_Name()
0x4a954  ldc.i4.0
0x4a955  callvirt instance void WindowsTaskSchedulerInterop.ITaskFolder::DeleteFolder([hasfieldmarshal] string subFolderName, [in] int32 flags)
0x4a95a  leave.s  loc_4A98B
0x4a95c  stloc.s  5
0x4a95e  ldarg.0
0x4a95f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::logger
0x4a964  dup
0x4a965  brtrue.s loc_4A96A
0x4a967  pop
0x4a968  br.s     loc_4A989
0x4a96a  ldstr    aFailedToDelete_12// "Failed to delete task folder {0}: {1}"
0x4a96f  ldc.i4.2
0x4a970  newarr   [mscorlib]System.Object
0x4a975  dup
0x4a976  ldc.i4.0
0x4a977  ldloc.s  4
0x4a979  callvirt instance string WindowsTaskSchedulerInterop.ITaskFolder::get_Name()
0x4a97e  stelem.ref
0x4a97f  dup
0x4a980  ldc.i4.1
0x4a981  ldloc.s  5
0x4a983  stelem.ref
0x4a984  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x4a989  leave.s  loc_4A98B
0x4a98b  ldloc.0
0x4a98c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a991  brtrue.s loc_4A933
0x4a993  leave.s  loc_4A9A6
0x4a995  ldloc.0
0x4a996  isinst   [mscorlib]System.IDisposable
0x4a99b  stloc.3
0x4a99c  ldloc.3
0x4a99d  brfalse.s loc_4A9A5
0x4a99f  ldloc.3
0x4a9a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a9a5  endfinally
0x4a9a6  ret
```
