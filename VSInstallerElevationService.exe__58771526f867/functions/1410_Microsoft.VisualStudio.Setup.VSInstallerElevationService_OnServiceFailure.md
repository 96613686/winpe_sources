# Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnServiceFailure

- ea: `0x1410`
- end: `0x1459`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnServiceFailure`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`

## callees

- `0x1410`
- `0x15f0`

## string_xrefs

- `0x1423`: `Elevation service manager ran into an error.`
- `0x1447`: `Elevation service manager ran into an error. Stopping the elevation service`

## pseudocode

```c

```

## disassembly

```asm
0x1410  ldarg.0
0x1411  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x1416  dup
0x1417  brtrue.s loc_141C
0x1419  pop
0x141a  br.s     loc_142E
0x141c  ldarg.1
0x141d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1422  ldarg.1
0x1423  ldstr    aElevationServi_0// "Elevation service manager ran into an e"...
0x1428  ldc.i4.1
0x1429  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x142e  ldarg.0
0x142f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x1434  dup
0x1435  brtrue.s loc_143A
0x1437  pop
0x1438  br.s     loc_143F
0x143a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x143f  ldarg.0
0x1440  ldnull
0x1441  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x1446  ldarg.0
0x1447  ldstr    aElevationServi_1// "Elevation service manager ran into an e"...
0x144c  ldarg.1
0x144d  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogError(string message, class [mscorlib]System.Exception ex)
0x1452  ldarg.0
0x1453  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Stop()
0x1458  ret
```
