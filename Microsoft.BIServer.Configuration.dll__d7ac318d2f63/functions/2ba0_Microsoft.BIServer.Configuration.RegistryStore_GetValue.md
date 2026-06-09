# Microsoft.BIServer.Configuration.RegistryStore::GetValue

- ea: `0x2ba0`
- end: `0x2bbb`
- name: `Microsoft.BIServer.Configuration.RegistryStore::GetValue`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2ae0`
- `0x2ba0`

## pseudocode

```c

```

## disassembly

```asm
0x2ba0  ldarg.0
0x2ba1  ldarg.1
0x2ba2  call     instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::GetSubKey(string subKeyName)
0x2ba7  stloc.0
0x2ba8  ldloc.0
0x2ba9  brfalse.s loc_2BB9
0x2bab  ldloc.0
0x2bac  ldarg.2
0x2bad  ldnull
0x2bae  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x2bb3  castclass [mscorlib]System.String
0x2bb8  ret
0x2bb9  ldnull
0x2bba  ret
```
