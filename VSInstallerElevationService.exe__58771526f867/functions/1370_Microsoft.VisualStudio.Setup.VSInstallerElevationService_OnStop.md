# Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnStop

- ea: `0x1370`
- end: `0x13f9`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnStop`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xcf0`
- `0xf20`
- `0x1370`
- `0x15d0`

## string_xrefs

- `0x1371`: `Stopping elevation service...`
- `0x13bc`: `Successfully shutting down service.`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldarg.0
0x1371  ldstr    aStoppingElevat// "Stopping elevation service..."
0x1376  call     T0x2B000005
0x137b  call     instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage(string message, string[] args)
0x1380  ldarg.0
0x1381  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x1386  brfalse.s loc_139F
0x1388  ldarg.0
0x1389  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x138e  ldarg.0
0x138f  ldftn    instance void Microsoft.VisualStudio.Setup.VSInstallerElevationService::OnServiceFailure(class [mscorlib]System.Exception ex)
0x1395  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Exception>::.ctor(object, native int)
0x139a  callvirt instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::remove_RunError(class [mscorlib]System.Action`1<class [mscorlib]System.Exception> value)
0x139f  ldarg.0
0x13a0  ldfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager Microsoft.VisualStudio.Setup.VSInstallerElevationService::serviceManager
0x13a5  dup
0x13a6  brtrue.s loc_13AB
0x13a8  pop
0x13a9  br.s     loc_13B0
0x13ab  call     instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::Dispose()
0x13b0  ldarg.0
0x13b1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x13b6  dup
0x13b7  brtrue.s loc_13BC
0x13b9  pop
0x13ba  br.s     loc_13C6
0x13bc  ldstr    aSuccessfullySh// "Successfully shutting down service."
0x13c1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x13c6  ldarg.0
0x13c7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.VSInstallerElevationService::runOperation
0x13cc  dup
0x13cd  brtrue.s loc_13D2
0x13cf  pop
0x13d0  br.s     loc_13D7
0x13d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d7  ldarg.0
0x13d8  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionHandler Microsoft.VisualStudio.Setup.VSInstallerElevationService::exceptionHandler
0x13dd  dup
0x13de  brtrue.s loc_13E3
0x13e0  pop
0x13e1  br.s     loc_13E8
0x13e3  call     instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionHandler::Dispose()
0x13e8  ldarg.0
0x13e9  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x13ee  dup
0x13ef  brtrue.s loc_13F3
0x13f1  pop
0x13f2  ret
0x13f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13f8  ret
```
