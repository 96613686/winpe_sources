# Microsoft.VisualStudio.Setup.ElevationServiceManager::SavePipeName

- ea: `0xdf0`
- end: `0xe8d`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::SavePipeName`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xd60`

## callees

- `0xdf0`

## string_xrefs

- `0xe07`: `Failed to save pipe name. Couldn't open HKLM.`
- `0xe16`: `Failed to open HKLM.`
- `0xe37`: `Failed to save pipe name. Couldn't open {0}`
- `0xe4f`: `Failed to create `

## pseudocode

```c

```

## disassembly

```asm
0xdf0  ldarg.0
0xdf1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.ElevationServiceManager::registry
0xdf6  ldc.i4.2
0xdf7  ldc.i4.0
0xdf8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0xdfd  stloc.0
0xdfe  ldloc.0
0xdff  brtrue.s loc_E21
0xe01  ldarg.0
0xe02  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xe07  ldstr    aFailedToSavePi// "Failed to save pipe name. Couldn't open"...
0xe0c  call     T0x2B000003
0xe11  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0xe16  ldstr    aFailedToOpenHk// "Failed to open HKLM."
0xe1b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe20  throw
0xe21  ldloc.0
0xe22  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0xe27  ldc.i4.0
0xe28  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0xe2d  stloc.1
0xe2e  ldloc.1
0xe2f  brtrue.s loc_E69
0xe31  ldarg.0
0xe32  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xe37  ldstr    aFailedToSavePi_0// "Failed to save pipe name. Couldn't open"...
0xe3c  ldc.i4.1
0xe3d  newarr   [mscorlib]System.Object
0xe42  dup
0xe43  ldc.i4.0
0xe44  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0xe49  stelem.ref
0xe4a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0xe4f  ldstr    aFailedToCreate_2// "Failed to create "
0xe54  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0xe59  ldstr    aKey// " key."
0xe5e  call     string [mscorlib]System.String::Concat(string, string, string)
0xe63  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0xe68  throw
0xe69  ldloc.1
0xe6a  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServicePipeNameRegistryValue
0xe6f  ldarg.1
0xe70  ldc.i4.1
0xe71  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0xe76  leave.s  loc_E8C
0xe78  ldloc.1
0xe79  brfalse.s loc_E81
0xe7b  ldloc.1
0xe7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe81  endfinally
0xe82  ldloc.0
0xe83  brfalse.s loc_E8B
0xe85  ldloc.0
0xe86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8b  endfinally
0xe8c  ret
```
