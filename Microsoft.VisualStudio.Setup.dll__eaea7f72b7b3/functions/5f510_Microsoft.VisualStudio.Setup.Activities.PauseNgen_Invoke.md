# Microsoft.VisualStudio.Setup.Activities.PauseNgen::Invoke

- ea: `0x5f510`
- end: `0x5f5c8`
- name: `Microsoft.VisualStudio.Setup.Activities.PauseNgen::Invoke`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x305c0`
- `0x3e1c0`
- `0x3e1e0`
- `0x596d0`
- `0x596f0`
- `0x5f510`

## string_xrefs

- `0x5f53e`: `NGEN service has been paused`
- `0x5f559`: `Failed to pause NGEN service`
- `0x5f59d`: `Continue NGEN service successfully`
- `0x5f5b8`: `Failed to continue NGEN service`

## pseudocode

```c

```

## disassembly

```asm
0x5f510  ldarg.0
0x5f511  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f516  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture> Microsoft.VisualStudio.Setup.Installer.NgenHelper::GetArchitectures(class [mscorlib]System.IServiceProvider serviceProvider)
0x5f51b  stloc.0
0x5f51c  ldarg.0
0x5f51d  ldfld    bool Microsoft.VisualStudio.Setup.Activities.PauseNgen::pause
0x5f522  brfalse.s loc_5F569
0x5f524  ldarg.0
0x5f525  ldfld    class Microsoft.VisualStudio.Setup.Services.INgenService Microsoft.VisualStudio.Setup.Activities.PauseNgen::ngenService
0x5f52a  ldloc.0
0x5f52b  ldarg.1
0x5f52c  callvirt instance bool Microsoft.VisualStudio.Setup.Services.INgenService::PauseNgenTasks(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture> architectures, valuetype [mscorlib]System.Threading.CancellationToken token)
0x5f531  brfalse.s loc_5F54E
0x5f533  ldarg.0
0x5f534  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f539  dup
0x5f53a  brtrue.s loc_5F53E
0x5f53c  pop
0x5f53d  ret
0x5f53e  ldstr    aNgenServiceHas// "NGEN service has been paused"
0x5f543  call     T0x2B000003
0x5f548  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5f54d  ret
0x5f54e  ldarg.0
0x5f54f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f554  dup
0x5f555  brtrue.s loc_5F559
0x5f557  pop
0x5f558  ret
0x5f559  ldstr    aFailedToPauseN// "Failed to pause NGEN service"
0x5f55e  call     T0x2B000003
0x5f563  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5f568  ret
0x5f569  ldarg.0
0x5f56a  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5f56f  ldc.i4.1
0x5f570  call     T0x2B00012B
0x5f575  ldarg.0
0x5f576  ldfld    string Microsoft.VisualStudio.Setup.Activities.PauseNgen::installDirectory
0x5f57b  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRestartManager::CheckSystemPendingReboot(string)
0x5f580  brfalse.s loc_5F583
0x5f582  ret
0x5f583  ldarg.0
0x5f584  ldfld    class Microsoft.VisualStudio.Setup.Services.INgenService Microsoft.VisualStudio.Setup.Activities.PauseNgen::ngenService
0x5f589  ldloc.0
0x5f58a  ldarg.1
0x5f58b  callvirt instance bool Microsoft.VisualStudio.Setup.Services.INgenService::ContinueNgenTasks(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.NgenArchitecture> architectures, valuetype [mscorlib]System.Threading.CancellationToken token)
0x5f590  brfalse.s loc_5F5AD
0x5f592  ldarg.0
0x5f593  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f598  dup
0x5f599  brtrue.s loc_5F59D
0x5f59b  pop
0x5f59c  ret
0x5f59d  ldstr    aContinueNgenSe// "Continue NGEN service successfully"
0x5f5a2  call     T0x2B000003
0x5f5a7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5f5ac  ret
0x5f5ad  ldarg.0
0x5f5ae  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f5b3  dup
0x5f5b4  brtrue.s loc_5F5B8
0x5f5b6  pop
0x5f5b7  ret
0x5f5b8  ldstr    aFailedToContin// "Failed to continue NGEN service"
0x5f5bd  call     T0x2B000003
0x5f5c2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5f5c7  ret
```
