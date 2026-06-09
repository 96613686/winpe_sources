# Microsoft.VisualStudio.Setup.Services.Extensions::OpenKey

- ea: `0x112f0`
- end: `0x1134e`
- name: `Microsoft.VisualStudio.Setup.Services.Extensions::OpenKey`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x11350`

## callees

- `0xc1a0`
- `0xc1d0`
- `0x112f0`
- `0x11de0`
- `0x11df0`
- `0x11e50`

## string_xrefs

- `0x112f1`: `registry`
- `0x112fc`: `registryKey`
- `0x11323`: `registryKey`
- `0x11313`: `The registry key "`

## pseudocode

```c

```

## disassembly

```asm
0x112f0  ldarg.0
0x112f1  ldstr    aRegistry// "registry"
0x112f6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x112fb  ldarg.1
0x112fc  ldstr    aRegistrykey_0// "registryKey"
0x11301  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0x11306  ldarg.0
0x11307  ldarg.1
0x11308  ldloca.s 1
0x1130a  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.RegistryHive Microsoft.VisualStudio.Setup.Services.IRegistry::ExtractBaseHive(string registryKey, [out] string& keyWithoutBaseHive)
0x1130f  stloc.0
0x11310  ldloc.0
0x11311  brtrue.s loc_1132E
0x11313  ldstr    aTheRegistryKey// "The registry key \""
0x11318  ldarg.1
0x11319  ldstr    aIsInvalid// "\" is invalid"
0x1131e  call     string [mscorlib]System.String::Concat(string, string, string)
0x11323  ldstr    aRegistrykey_0// "registryKey"
0x11328  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1132d  throw
0x1132e  ldarg.0
0x1132f  ldloc.0
0x11330  ldarg.2
0x11331  callvirt instance class Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype Microsoft.VisualStudio.Setup.Services.RegistryHive hive, valuetype Microsoft.VisualStudio.Setup.Services.RegistryView view)
0x11336  stloc.2
0x11337  ldloc.2
0x11338  ldloc.1
0x11339  ldarg.3
0x1133a  callvirt instance class Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string path, [opt] bool writable)
0x1133f  stloc.3
0x11340  leave.s  loc_1134C
0x11342  ldloc.2
0x11343  brfalse.s loc_1134B
0x11345  ldloc.2
0x11346  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1134b  endfinally
0x1134c  ldloc.3
0x1134d  ret
```
