# Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateConnectionValidator

- ea: `0x1610`
- end: `0x165a`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateConnectionValidator`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x1610  ldarg.0
0x1611  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1616  ldc.i4.1
0x1617  call     T0x2B000013
0x161c  stloc.0
0x161d  ldarg.0
0x161e  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1623  ldc.i4.1
0x1624  call     T0x2B000014
0x1629  stloc.1
0x162a  ldarg.0
0x162b  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1630  ldc.i4.1
0x1631  call     T0x2B000015
0x1636  ldarg.0
0x1637  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x163c  ldc.i4.1
0x163d  call     T0x2B000017
0x1642  stloc.2
0x1643  ldarg.0
0x1644  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1649  ldc.i4.1
0x164a  call     T0x2B000006
0x164f  stloc.3
0x1650  ldloc.0
0x1651  ldloc.1
0x1652  ldloc.2
0x1653  ldloc.3
0x1654  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.InstallerRpcValidator::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry)
0x1659  ret
```
