# Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage

- ea: `0x15d0`
- end: `0x15e6`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::LogMessage`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`
- `0x1370`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  ldarg.0
0x15d1  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x15d6  ldc.i4.1
0x15d7  call     T0x2B000017
0x15dc  ldarg.1
0x15dd  ldarg.2
0x15de  stloc.0
0x15df  ldloc.0
0x15e0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x15e5  ret
```
