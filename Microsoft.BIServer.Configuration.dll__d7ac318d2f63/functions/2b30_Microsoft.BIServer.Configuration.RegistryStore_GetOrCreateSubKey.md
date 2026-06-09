# Microsoft.BIServer.Configuration.RegistryStore::GetOrCreateSubKey

- ea: `0x2b30`
- end: `0x2b6d`
- name: `Microsoft.BIServer.Configuration.RegistryStore::GetOrCreateSubKey`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2a30`
- `0x2b70`
- `0x2b80`

## callees

- `0x2b30`

## pseudocode

```c

```

## disassembly

```asm
0x2b30  ldarg.0
0x2b31  ldfld    class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::_storeTop
0x2b36  stloc.0
0x2b37  ldarg.1
0x2b38  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b3d  brtrue.s loc_2B6B
0x2b3f  ldarg.1
0x2b40  ldc.i4.1
0x2b41  newarr   [mscorlib]System.Char
0x2b46  dup
0x2b47  ldc.i4.0
0x2b48  ldc.i4.s 0x5C
0x2b4a  stelem.i2
0x2b4b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2b50  stloc.1
0x2b51  ldc.i4.0
0x2b52  stloc.2
0x2b53  br.s     loc_2B65
0x2b55  ldloc.1
0x2b56  ldloc.2
0x2b57  ldelem.ref
0x2b58  stloc.3
0x2b59  ldloc.0
0x2b5a  ldloc.3
0x2b5b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::CreateSubKey(string)
0x2b60  stloc.0
0x2b61  ldloc.2
0x2b62  ldc.i4.1
0x2b63  add
0x2b64  stloc.2
0x2b65  ldloc.2
0x2b66  ldloc.1
0x2b67  ldlen
0x2b68  conv.i4
0x2b69  blt.s    loc_2B55
0x2b6b  ldloc.0
0x2b6c  ret
```
