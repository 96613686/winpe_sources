# Microsoft.BIServer.Configuration.RegistryStore::.ctor

- ea: `0x2a30`
- end: `0x2a53`
- name: `Microsoft.BIServer.Configuration.RegistryStore::.ctor`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2f40`

## callees

- `0x2a30`
- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2a30  ldarg.0
0x2a31  call     instance void [mscorlib]System.Object::.ctor()
0x2a36  ldarg.0
0x2a37  ldarg.1
0x2a38  stfld    class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::_storeTop
0x2a3d  ldarg.2
0x2a3e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a43  brtrue.s loc_2A52
0x2a45  ldarg.0
0x2a46  ldarg.0
0x2a47  ldarg.2
0x2a48  call     instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::GetOrCreateSubKey(string subKeyName)
0x2a4d  stfld    class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::_storeTop
0x2a52  ret
```
