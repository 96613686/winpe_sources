# Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateServices

- ea: `0x1460`
- end: `0x1548`
- name: `Microsoft.VisualStudio.Setup.VSInstallerElevationService::CreateServices`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1200`

## string_xrefs

- `0x14c1`: `installer_elevationservice`

## pseudocode

```c

```

## disassembly

```asm
0x1460  ldnull
0x1461  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider::.ctor(class [mscorlib]System.IServiceProvider)
0x1466  stloc.0
0x1467  ldloc.0
0x1468  ldsfld   class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IOperatingSystem [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.OperatingSystem::Default
0x146d  ldc.i4.0
0x146e  ldc.i4.0
0x146f  callvirt T0x2B00000A
0x1474  ldloc.0
0x1475  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.WindowsRegistry::Default
0x147a  ldc.i4.0
0x147b  ldc.i4.0
0x147c  callvirt T0x2B00000B
0x1481  ldloc.0
0x1482  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x1487  ldc.i4.0
0x1488  ldc.i4.0
0x1489  callvirt T0x2B00000C
0x148e  ldloc.0
0x148f  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProcessService::Default
0x1494  ldc.i4.0
0x1495  ldc.i4.0
0x1496  callvirt T0x2B00000D
0x149b  ldloc.0
0x149c  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::.ctor(class [mscorlib]System.IServiceProvider)
0x14a1  stloc.1
0x14a2  ldloc.0
0x14a3  ldloc.1
0x14a4  ldc.i4.0
0x14a5  ldc.i4.0
0x14a6  callvirt T0x2B00000E
0x14ab  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RemoteSettingsConstants::RemoteSettingsFileName
0x14b0  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.RemoteSettingsService::.ctor(string)
0x14b5  stloc.2
0x14b6  ldloc.0
0x14b7  ldloc.2
0x14b8  ldc.i4.0
0x14b9  ldc.i4.0
0x14ba  callvirt T0x2B00000F
0x14bf  ldloc.0
0x14c0  ldnull
0x14c1  ldstr    aInstallerEleva// "installer_elevationservice"
0x14c6  ldc.i4.5
0x14c7  ldc.i4   0xBB8
0x14cc  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::OpenFileLogger(class [mscorlib]System.IServiceProvider, string, string, int32, int32)
0x14d1  stloc.3
0x14d2  ldloc.0
0x14d3  ldloc.3
0x14d4  ldc.i4.0
0x14d5  ldc.i4.0
0x14d6  callvirt T0x2B000010
0x14db  ldloc.3
0x14dc  ldstr    aTelemetrySessi// "Telemetry session ID: {0}"
0x14e1  ldc.i4.1
0x14e2  newarr   [mscorlib]System.Object
0x14e7  dup
0x14e8  ldc.i4.0
0x14e9  ldloc.1
0x14ea  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySessionID()
0x14ef  stelem.ref
0x14f0  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::WriteVerbose(string, object[])
0x14f5  ldnull
0x14f6  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Security.SignatureManager::.ctor(class [mscorlib]System.IServiceProvider)
0x14fb  stloc.s  4
0x14fd  ldloc.s  4
0x14ff  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Security.SignatureManager::AddDefaultVerifiers()
0x1504  ldloc.0
0x1505  ldloc.s  4
0x1507  ldc.i4.0
0x1508  ldc.i4.0
0x1509  callvirt T0x2B000011
0x150e  ldloc.0
0x150f  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PolicyService::.ctor(class [mscorlib]System.IServiceProvider)
0x1514  stloc.s  5
0x1516  ldloc.0
0x1517  ldloc.s  5
0x1519  ldc.i4.0
0x151a  ldc.i4.0
0x151b  callvirt T0x2B000012
0x1520  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionArtifacts::.ctor()
0x1525  dup
0x1526  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionArtifacts::get_LogFiles()
0x152b  ldloc.3
0x152c  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::get_Path()
0x1531  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x1536  stloc.s  6
0x1538  ldarg.0
0x1539  ldloc.0
0x153a  ldloc.s  6
0x153c  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionHandler::.ctor(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionArtifacts)
0x1541  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.UnhandledExceptionHandler Microsoft.VisualStudio.Setup.VSInstallerElevationService::exceptionHandler
0x1546  ldloc.0
0x1547  ret
```
