# Microsoft.VisualStudio.Setup.VsixAutoUpdaterScheduler::Schedule

- ea: `0x1da10`
- end: `0x1da99`
- name: `Microsoft.VisualStudio.Setup.VsixAutoUpdaterScheduler::Schedule`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5dc30`

## callees

- `0x1da10`
- `0x1daa0`
- `0x3f060`
- `0x3f090`
- `0x3f0a0`
- `0x49250`
- `0x49260`
- `0x49270`

## string_xrefs

- `0x1da3d`: `Found VSIX Auto Updater scheduled task; skipping registration`
- `0x1da7c`: `Failed to create the VSIX Auto Updater task: `

## pseudocode

```c

```

## disassembly

```asm
0x1da10  ldarg.0
0x1da11  callvirt instance bool Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::ShouldRun()
0x1da16  brtrue.s loc_1DA19
0x1da18  ret
0x1da19  ldarg.0
0x1da1a  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1da1f  ldsfld   string Microsoft.VisualStudio.Setup.VsixAutoUpdaterScheduler::DefinitionName
0x1da24  ldsfld   string Microsoft.VisualStudio.Setup.VsixAutoUpdaterScheduler::VsixAutoUpdateTaskPath
0x1da29  ldloca.s 1
0x1da2b  callvirt instance bool Microsoft.VisualStudio.Setup.Services.ITaskScheduler::TryGetTaskDetails(string name, string directory, [out] class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails& taskDetails)
0x1da30  brfalse.s loc_1DA4D
0x1da32  ldarg.0
0x1da33  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1da38  dup
0x1da39  brtrue.s loc_1DA3D
0x1da3b  pop
0x1da3c  ret
0x1da3d  ldstr    aFoundVsixAutoU// "Found VSIX Auto Updater scheduled task;"...
0x1da42  call     T0x2B000003
0x1da47  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1da4c  ret
0x1da4d  ldarg.0
0x1da4e  call     instance class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition Microsoft.VisualStudio.Setup.VsixAutoUpdaterScheduler::GetTaskDefinition()
0x1da53  stloc.0
0x1da54  ldarg.0
0x1da55  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1da5a  ldloc.0
0x1da5b  ldc.i4.0
0x1da5c  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITaskScheduler::Create(class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition definition, [opt] bool excludeUpdate)
0x1da61  ldarg.0
0x1da62  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1da67  ldloc.0
0x1da68  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITaskScheduler::RemoveDuplicates(class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition taskDefinition)
0x1da6d  leave.s  loc_1DA98
0x1da6f  stloc.2
0x1da70  ldarg.0
0x1da71  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1da76  dup
0x1da77  brtrue.s loc_1DA7C
0x1da79  pop
0x1da7a  br.s     loc_1DA96
0x1da7c  ldstr    aFailedToCreate_1// "Failed to create the VSIX Auto Updater "...
0x1da81  ldloc.2
0x1da82  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1da87  call     string [mscorlib]System.String::Concat(string, string)
0x1da8c  call     T0x2B000003
0x1da91  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1da96  leave.s  loc_1DA98
0x1da98  ret
```
