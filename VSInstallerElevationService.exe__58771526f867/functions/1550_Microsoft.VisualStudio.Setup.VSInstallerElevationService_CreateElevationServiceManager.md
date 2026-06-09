# Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateElevationServiceManager

- ea: `0x1550`
- end: `0x15c5`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateElevationServiceManager`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`

## callees

- `0xc50`
- `0x1610`
- `0x1b50`
- `0x1c00`

## pseudocode

```c

```

## disassembly

```asm
0x1550  ldarg.0
0x1551  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1556  ldc.i4.1
0x1557  call     T0x2B000013
0x155c  ldarg.0
0x155d  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1562  ldc.i4.1
0x1563  call     T0x2B000014
0x1568  stloc.0
0x1569  ldarg.0
0x156a  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x156f  ldc.i4.1
0x1570  call     T0x2B000015
0x1575  stloc.1
0x1576  ldarg.0
0x1577  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x157c  ldc.i4.1
0x157d  call     T0x2B000016
0x1582  stloc.2
0x1583  ldarg.0
0x1584  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1589  ldc.i4.1
0x158a  call     T0x2B000006
0x158f  stloc.3
0x1590  ldarg.0
0x1591  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceContainer Microsoft.VisualStudio.Setup.VSInstallerElevationService::services
0x1596  ldc.i4.1
0x1597  call     T0x2B000017
0x159c  stloc.s  4
0x159e  ldloc.0
0x159f  ldloc.1
0x15a0  ldloc.3
0x15a1  ldloc.s  4
0x15a3  newobj   instance void Microsoft.VisualStudio.Setup.Services.StreamJsonRpcFactory::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager signatureVerifier, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService processService, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x15a8  stloc.s  5
0x15aa  ldarg.0
0x15ab  call     instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.IRpcConnectionValidator Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateConnectionValidator()
0x15b0  stloc.s  6
0x15b2  newobj   instance void Microsoft.VisualStudio.Setup.Services.PipeFactory::.ctor()
0x15b7  ldloc.2
0x15b8  ldloc.s  5
0x15ba  ldloc.s  6
0x15bc  ldloc.3
0x15bd  ldloc.s  4
0x15bf  newobj   instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::.ctor(class Microsoft.VisualStudio.Setup.Services.IPipeFactory pipeFactory, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry registry, class Microsoft.VisualStudio.Setup.Services.IStreamJsonRpcFactory rpcFactory, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.Rpc.IRpcConnectionValidator clientValidator, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x15c4  ret
```
