# Microsoft.VisualStudio.Setup.ElevationServiceManager::TryClearPipeName

- ea: `0xe90`
- end: `0xef4`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::TryClearPipeName`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf30`

## callees

- `0xe90`

## pseudocode

```c

```

## disassembly

```asm
0xe90  ldarg.0
0xe91  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.ElevationServiceManager::registry
0xe96  ldc.i4.2
0xe97  ldc.i4.0
0xe98  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0xe9d  stloc.0
0xe9e  ldloc.0
0xe9f  brtrue.s loc_EA3
0xea1  leave.s  loc_EF3
0xea3  ldloc.0
0xea4  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0xea9  ldc.i4.1
0xeaa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0xeaf  stloc.1
0xeb0  ldloc.1
0xeb1  brtrue.s loc_EB5
0xeb3  leave.s  loc_EF3
0xeb5  ldloc.1
0xeb6  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServicePipeNameRegistryValue
0xebb  ldc.i4.0
0xebc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::DeleteValue(string, bool)
0xec1  leave.s  loc_ECD
0xec3  ldloc.1
0xec4  brfalse.s loc_ECC
0xec6  ldloc.1
0xec7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xecc  endfinally
0xecd  leave.s  loc_ED9
0xecf  ldloc.0
0xed0  brfalse.s loc_ED8
0xed2  ldloc.0
0xed3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xed8  endfinally
0xed9  leave.s  loc_EF3
0xedb  pop
0xedc  ldarg.0
0xedd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xee2  ldstr    aFailedToClearP// "Failed to clear pipe name."
0xee7  call     T0x2B000003
0xeec  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0xef1  leave.s  loc_EF3
0xef3  ret
```
