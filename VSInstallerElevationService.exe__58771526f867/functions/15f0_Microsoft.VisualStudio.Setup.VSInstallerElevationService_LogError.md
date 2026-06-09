# Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogError

- ea: `0x15f0`
- end: `0x1609`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogError`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`
- `0x1410`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.0
0x15f1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x15f6  ldc.i4.1
0x15f7  call     T0x2B000017
0x15fc  ldarg.2
0x15fd  ldarg.1
0x15fe  call     T0x2B000003
0x1603  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x1608  ret
```
