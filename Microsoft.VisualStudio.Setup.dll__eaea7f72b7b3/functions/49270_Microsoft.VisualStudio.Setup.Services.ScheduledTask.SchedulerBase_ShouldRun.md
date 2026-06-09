# Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::ShouldRun

- ea: `0x49270`
- end: `0x492fa`
- name: `Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::ShouldRun`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2fa0`
- `0x1c4c0`
- `0x1c950`
- `0x1da10`
- `0x1db20`

## callees

- `0x3e950`
- `0x49220`
- `0x49240`
- `0x49250`
- `0x49270`

## string_xrefs

- `0x49298`: `Skipping scheduling task in container.`
- `0x492d7`: `Failed to create scheduled task: `

## pseudocode

```c

```

## disassembly

```asm
0x49270  ldarg.0
0x49271  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Services()
0x49276  ldc.i4.0
0x49277  call     T0x2B000053
0x4927c  dup
0x4927d  brtrue.s loc_49285
0x4927f  pop
0x49280  ldsfld   class Microsoft.VisualStudio.Setup.Services.IOperatingSystem Microsoft.VisualStudio.Setup.Services.OperatingSystem::Default
0x49285  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IOperatingSystem::get_InContainer()
0x4928a  brfalse.s loc_492A9
0x4928c  ldarg.0
0x4928d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x49292  dup
0x49293  brtrue.s loc_49298
0x49295  pop
0x49296  br.s     loc_492A7
0x49298  ldstr    aSkippingSchedu// "Skipping scheduling task in container."
0x4929d  call     T0x2B000003
0x492a2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x492a7  ldc.i4.0
0x492a8  ret
0x492a9  ldarg.0
0x492aa  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Services()
0x492af  ldc.i4.0
0x492b0  call     T0x2B00000C
0x492b5  dup
0x492b6  brtrue.s loc_492BE
0x492b8  pop
0x492b9  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x492be  ldarg.0
0x492bf  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_ActionPath()
0x492c4  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x492c9  brtrue.s loc_492F8
0x492cb  ldarg.0
0x492cc  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x492d1  dup
0x492d2  brtrue.s loc_492D7
0x492d4  pop
0x492d5  br.s     loc_492F6
0x492d7  ldstr    aFailedToCreate_11// "Failed to create scheduled task: "
0x492dc  ldarg.0
0x492dd  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_ActionPath()
0x492e2  ldstr    aCannotBeFound// " cannot be found."
0x492e7  call     string [mscorlib]System.String::Concat(string, string, string)
0x492ec  call     T0x2B000003
0x492f1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x492f6  ldc.i4.0
0x492f7  ret
0x492f8  ldc.i4.1
0x492f9  ret
```
