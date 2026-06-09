# Microsoft.VisualStudio.Setup.Services.ElevationRequestService::StartInstallerServiceAsync

- ea: `0x16e0`
- end: `0x172c`
- name: `Microsoft.VisualStudio.Setup.Services.ElevationRequestService::StartInstallerServiceAsync`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x16e0`
- `0x1860`

## string_xrefs

- `0x16fa`: `Received request to start elevated service.`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldarg.0
0x16e1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Services.ElevationRequestService::telemetry
0x16e6  ldsfld   string Microsoft.VisualStudio.Setup.TelemetryConstants::ElevationRequestEventName
0x16eb  ldnull
0x16ec  ldc.i4.0
0x16ed  ldc.i4.0
0x16ee  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x16f3  stloc.0
0x16f4  ldarg.0
0x16f5  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ElevationRequestService::logger
0x16fa  ldstr    aReceivedReques// "Received request to start elevated serv"...
0x16ff  call     T0x2B000003
0x1704  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x1709  ldarga.s 2
0x170b  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x1710  ldarg.0
0x1711  ldloc.0
0x1712  ldarg.1
0x1713  call     instance class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationResult Microsoft.VisualStudio.Setup.Services.ElevationRequestService::ValidateAndStartService(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationRequest request)
0x1718  call     T0x2B000018
0x171d  stloc.1
0x171e  leave.s  loc_172A
0x1720  ldloc.0
0x1721  brfalse.s loc_1729
0x1723  ldloc.0
0x1724  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1729  endfinally
0x172a  ldloc.1
0x172b  ret
```
