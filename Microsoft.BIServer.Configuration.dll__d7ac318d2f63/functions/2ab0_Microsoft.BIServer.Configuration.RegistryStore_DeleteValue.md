# Microsoft.BIServer.Configuration.RegistryStore::DeleteValue

- ea: `0x2ab0`
- end: `0x2ae0`
- name: `Microsoft.BIServer.Configuration.RegistryStore::DeleteValue`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x2ab0`
- `0x2ae0`

## string_xrefs

- `0x2ac5`: `Could not remove registry key {0} from parent {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2ab0  ldarg.0
0x2ab1  ldarg.1
0x2ab2  call     instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::GetSubKey(string subKeyName)
0x2ab7  stloc.0
0x2ab8  ldloc.0
0x2ab9  brfalse.s loc_2AC3
0x2abb  ldloc.0
0x2abc  ldarg.2
0x2abd  ldc.i4.0
0x2abe  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x2ac3  leave.s  loc_2ADF
0x2ac5  ldstr    aCouldNotRemove// "Could not remove registry key {0} from "...
0x2aca  ldc.i4.2
0x2acb  newarr   [mscorlib]System.Object
0x2ad0  dup
0x2ad1  ldc.i4.0
0x2ad2  ldarg.2
0x2ad3  stelem.ref
0x2ad4  dup
0x2ad5  ldc.i4.1
0x2ad6  ldarg.1
0x2ad7  stelem.ref
0x2ad8  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Warning(class [mscorlib]System.Exception, string, object[])
0x2add  leave.s  loc_2ADF
0x2adf  ret
```
