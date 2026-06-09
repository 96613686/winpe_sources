# Microsoft.VisualStudio.Setup.Activities.ScheduleTasks::CleanupObsoleteUpdateConfigurationTasks

- ea: `0x60500`
- end: `0x6056b`
- name: `Microsoft.VisualStudio.Setup.Activities.ScheduleTasks::CleanupObsoleteUpdateConfigurationTasks`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x603d0`

## callees

- `0x1c450`
- `0x1c5b0`
- `0x60500`

## string_xrefs

- `0x60525`: `Failed to clean up obsolete UpdateConfiguration tasks: `
- `0x60556`: `Failed to clean up obsolete UpdateConfiguration tasks`

## pseudocode

```c

```

## disassembly

```asm
0x60500  ldarg.0
0x60501  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.ScheduleTasks::services
0x60506  newobj   instance void Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::.ctor(class [mscorlib]System.IServiceProvider services)
0x6050b  callvirt instance void Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::CleanupObsoleteTasks()
0x60510  leave.s  loc_6056A
0x60512  stloc.0
0x60513  ldarg.0
0x60514  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.ScheduleTasks::services
0x60519  ldc.i4.0
0x6051a  call     T0x2B000001
0x6051f  dup
0x60520  brtrue.s loc_60525
0x60522  pop
0x60523  br.s     loc_6053F
0x60525  ldstr    aFailedToCleanU// "Failed to clean up obsolete UpdateConfi"...
0x6052a  ldloc.0
0x6052b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x60530  call     string [mscorlib]System.String::Concat(string, string)
0x60535  call     T0x2B000003
0x6053a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x6053f  ldarg.0
0x60540  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.ScheduleTasks::services
0x60545  ldc.i4.0
0x60546  call     T0x2B000039
0x6054b  dup
0x6054c  brtrue.s loc_60551
0x6054e  pop
0x6054f  br.s     loc_60568
0x60551  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x60556  ldstr    aFailedToCleanU_0// "Failed to clean up obsolete UpdateConfi"...
0x6055b  ldnull
0x6055c  ldloc.0
0x6055d  ldnull
0x6055e  ldc.i4.0
0x6055f  ldnull
0x60560  ldc.i4.0
0x60561  ldnull
0x60562  ldc.i4.0
0x60563  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x60568  leave.s  loc_6056A
0x6056a  ret
```
