# Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::RemoveDuplicates

- ea: `0x4a420`
- end: `0x4a5f7`
- name: `Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::RemoveDuplicates`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x3edb0`
- `0x3edd0`
- `0x4a420`
- `0x4a880`
- `0x4ae50`
- `0x4aeb0`
- `0x62280`
- `0x622a0`
- `0x62470`
- `0x627c0`
- `0x627f0`
- `0x62820`
- `0x62980`
- `0x62a20`
- `0x62a30`

## string_xrefs

- `0x4a421`: `taskDefinition`
- `0x4a431`: `Directory`
- `0x4a5b2`: `Failed to delete duplicate task {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4a420  ldarg.1
0x4a421  ldstr    aTaskdefinition// "taskDefinition"
0x4a426  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x4a42b  ldarg.1
0x4a42c  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Directory()
0x4a431  ldstr    aDirectory_0// "Directory"
0x4a436  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x4a43b  ldarg.0
0x4a43c  call     instance class WindowsTaskSchedulerInterop.TaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetTaskScheduler()
0x4a441  stloc.0
0x4a442  ldarg.0
0x4a443  ldloc.0
0x4a444  ldarg.1
0x4a445  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Name()
0x4a44a  ldarg.1
0x4a44b  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Directory()
0x4a450  ldloca.s 1
0x4a452  call     instance bool Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::TryGetTask(class WindowsTaskSchedulerInterop.TaskScheduler scheduler, string name, string directory, [out] class WindowsTaskSchedulerInterop.IRegisteredTask& task)
0x4a457  brtrue.s loc_4A45A
0x4a459  ret
0x4a45a  ldarg.0
0x4a45b  ldloc.0
0x4a45c  ldarg.1
0x4a45d  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Directory()
0x4a462  ldc.i4.1
0x4a463  call     instance class WindowsTaskSchedulerInterop.ITaskFolder Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetFolder(class WindowsTaskSchedulerInterop.TaskScheduler taskScheduler, string directory, [opt] bool createIfNotExist)
0x4a468  stloc.2
0x4a469  ldloc.2
0x4a46a  ldc.i4.1
0x4a46b  callvirt instance class WindowsTaskSchedulerInterop.IRegisteredTaskCollection WindowsTaskSchedulerInterop.ITaskFolder::GetTasks([hasfieldmarshal] int32)
0x4a470  stloc.3
0x4a471  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4a476  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x4a47b  stloc.s  4
0x4a47d  ldloc.1
0x4a47e  callvirt instance class WindowsTaskSchedulerInterop.ITaskDefinition WindowsTaskSchedulerInterop.IRegisteredTask::get_Definition()
0x4a483  callvirt instance class WindowsTaskSchedulerInterop.IActionCollection WindowsTaskSchedulerInterop.ITaskDefinition::get_Actions()
0x4a488  callvirt instance class [mscorlib]System.Collections.IEnumerator WindowsTaskSchedulerInterop.IActionCollection::GetEnumerator()
0x4a48d  stloc.s  5
0x4a48f  br.s     loc_4A4B2
0x4a491  ldloc.s  5
0x4a493  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a498  isinst   WindowsTaskSchedulerInterop.IExecAction
0x4a49d  stloc.s  6
0x4a49f  ldloc.s  6
0x4a4a1  brfalse.s loc_4A4B2
0x4a4a3  ldloc.s  4
0x4a4a5  ldloc.s  6
0x4a4a7  callvirt instance string WindowsTaskSchedulerInterop.IExecAction::get_Path()
0x4a4ac  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x4a4b1  pop
0x4a4b2  ldloc.s  5
0x4a4b4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a4b9  brtrue.s loc_4A491
0x4a4bb  leave.s  loc_4A4D2
0x4a4bd  ldloc.s  5
0x4a4bf  isinst   [mscorlib]System.IDisposable
0x4a4c4  stloc.s  7
0x4a4c6  ldloc.s  7
0x4a4c8  brfalse.s loc_4A4D1
0x4a4ca  ldloc.s  7
0x4a4cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a4d1  endfinally
0x4a4d2  ldloc.3
0x4a4d3  callvirt instance class [mscorlib]System.Collections.IEnumerator WindowsTaskSchedulerInterop.IRegisteredTaskCollection::GetEnumerator()
0x4a4d8  stloc.s  5
0x4a4da  br       loc_4A5D3
0x4a4df  ldloc.s  5
0x4a4e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a4e6  isinst   WindowsTaskSchedulerInterop.IRegisteredTask
0x4a4eb  stloc.s  8
0x4a4ed  ldloc.s  8
0x4a4ef  brfalse  loc_4A5D3
0x4a4f4  ldloc.s  8
0x4a4f6  callvirt instance string WindowsTaskSchedulerInterop.IRegisteredTask::get_Name()
0x4a4fb  ldarg.1
0x4a4fc  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Name()
0x4a501  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a506  brtrue   loc_4A5D3
0x4a50b  ldloc.s  8
0x4a50d  callvirt instance class WindowsTaskSchedulerInterop.ITaskDefinition WindowsTaskSchedulerInterop.IRegisteredTask::get_Definition()
0x4a512  callvirt instance class WindowsTaskSchedulerInterop.IActionCollection WindowsTaskSchedulerInterop.ITaskDefinition::get_Actions()
0x4a517  callvirt instance int32 WindowsTaskSchedulerInterop.IActionCollection::get_Count()
0x4a51c  ldloc.1
0x4a51d  callvirt instance class WindowsTaskSchedulerInterop.ITaskDefinition WindowsTaskSchedulerInterop.IRegisteredTask::get_Definition()
0x4a522  callvirt instance class WindowsTaskSchedulerInterop.IActionCollection WindowsTaskSchedulerInterop.ITaskDefinition::get_Actions()
0x4a527  callvirt instance int32 WindowsTaskSchedulerInterop.IActionCollection::get_Count()
0x4a52c  bne.un   loc_4A5D3
0x4a531  ldc.i4.1
0x4a532  stloc.s  9
0x4a534  ldloc.s  8
0x4a536  callvirt instance class WindowsTaskSchedulerInterop.ITaskDefinition WindowsTaskSchedulerInterop.IRegisteredTask::get_Definition()
0x4a53b  callvirt instance class WindowsTaskSchedulerInterop.IActionCollection WindowsTaskSchedulerInterop.ITaskDefinition::get_Actions()
0x4a540  callvirt instance class [mscorlib]System.Collections.IEnumerator WindowsTaskSchedulerInterop.IActionCollection::GetEnumerator()
0x4a545  stloc.s  0xA
0x4a547  br.s     loc_4A570
0x4a549  ldloc.s  0xA
0x4a54b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a550  isinst   WindowsTaskSchedulerInterop.IExecAction
0x4a555  stloc.s  0xB
0x4a557  ldloc.s  0xB
0x4a559  brfalse.s loc_4A56B
0x4a55b  ldloc.s  4
0x4a55d  ldloc.s  0xB
0x4a55f  callvirt instance string WindowsTaskSchedulerInterop.IExecAction::get_Path()
0x4a564  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x4a569  brtrue.s loc_4A570
0x4a56b  ldc.i4.0
0x4a56c  stloc.s  9
0x4a56e  leave.s  loc_4A590
0x4a570  ldloc.s  0xA
0x4a572  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a577  brtrue.s loc_4A549
0x4a579  leave.s  loc_4A590
0x4a57b  ldloc.s  0xA
0x4a57d  isinst   [mscorlib]System.IDisposable
0x4a582  stloc.s  7
0x4a584  ldloc.s  7
0x4a586  brfalse.s loc_4A58F
0x4a588  ldloc.s  7
0x4a58a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a58f  endfinally
0x4a590  ldloc.s  9
0x4a592  brfalse.s loc_4A5D3
0x4a594  ldloc.2
0x4a595  ldloc.s  8
0x4a597  callvirt instance string WindowsTaskSchedulerInterop.IRegisteredTask::get_Name()
0x4a59c  ldc.i4.0
0x4a59d  callvirt instance void WindowsTaskSchedulerInterop.ITaskFolder::DeleteTask([in] [hasfieldmarshal] string Name, [in] int32 flags)
0x4a5a2  leave.s  loc_4A5D3
0x4a5a4  stloc.s  0xC
0x4a5a6  ldarg.0
0x4a5a7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::logger
0x4a5ac  dup
0x4a5ad  brtrue.s loc_4A5B2
0x4a5af  pop
0x4a5b0  br.s     loc_4A5D1
0x4a5b2  ldstr    aFailedToDelete_10// "Failed to delete duplicate task {0}: {1"...
0x4a5b7  ldc.i4.2
0x4a5b8  newarr   [mscorlib]System.Object
0x4a5bd  dup
0x4a5be  ldc.i4.0
0x4a5bf  ldloc.s  8
0x4a5c1  callvirt instance string WindowsTaskSchedulerInterop.IRegisteredTask::get_Name()
0x4a5c6  stelem.ref
0x4a5c7  dup
0x4a5c8  ldc.i4.1
0x4a5c9  ldloc.s  0xC
0x4a5cb  stelem.ref
0x4a5cc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x4a5d1  leave.s  loc_4A5D3
0x4a5d3  ldloc.s  5
0x4a5d5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a5da  brtrue   loc_4A4DF
0x4a5df  leave.s  loc_4A5F6
0x4a5e1  ldloc.s  5
0x4a5e3  isinst   [mscorlib]System.IDisposable
0x4a5e8  stloc.s  7
0x4a5ea  ldloc.s  7
0x4a5ec  brfalse.s loc_4A5F5
0x4a5ee  ldloc.s  7
0x4a5f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a5f5  endfinally
0x4a5f6  ret
```
