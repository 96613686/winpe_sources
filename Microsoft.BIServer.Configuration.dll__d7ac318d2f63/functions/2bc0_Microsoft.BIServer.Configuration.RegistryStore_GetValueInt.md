# Microsoft.BIServer.Configuration.RegistryStore::GetValueInt

- ea: `0x2bc0`
- end: `0x2bdf`
- name: `Microsoft.BIServer.Configuration.RegistryStore::GetValueInt`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2ae0`
- `0x2bc0`

## pseudocode

```c

```

## disassembly

```asm
0x2bc0  ldarg.0
0x2bc1  ldarg.1
0x2bc2  call     instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::GetSubKey(string subKeyName)
0x2bc7  stloc.0
0x2bc8  ldloc.0
0x2bc9  brfalse.s loc_2BD9
0x2bcb  ldloc.0
0x2bcc  ldarg.2
0x2bcd  ldnull
0x2bce  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x2bd3  unbox.any [mscorlib]System.Int32
0x2bd8  ret
0x2bd9  ldc.i4   0x80000000
0x2bde  ret
```
