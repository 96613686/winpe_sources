# Microsoft.BIServer.Configuration.RegistryStore::GetSubKey

- ea: `0x2ae0`
- end: `0x2b23`
- name: `Microsoft.BIServer.Configuration.RegistryStore::GetSubKey`
- size: `67`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2a60`
- `0x2ab0`
- `0x2ba0`
- `0x2bc0`
- `0x2be0`

## callees

- `0x2ae0`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldarg.0
0x2ae1  ldfld    class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.BIServer.Configuration.RegistryStore::_storeTop
0x2ae6  stloc.0
0x2ae7  ldarg.1
0x2ae8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2aed  brtrue.s loc_2B21
0x2aef  ldarg.1
0x2af0  ldc.i4.1
0x2af1  newarr   [mscorlib]System.Char
0x2af6  dup
0x2af7  ldc.i4.0
0x2af8  ldc.i4.s 0x5C
0x2afa  stelem.i2
0x2afb  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2b00  stloc.1
0x2b01  ldc.i4.0
0x2b02  stloc.2
0x2b03  br.s     loc_2B1B
0x2b05  ldloc.1
0x2b06  ldloc.2
0x2b07  ldelem.ref
0x2b08  stloc.3
0x2b09  ldloc.0
0x2b0a  ldloc.3
0x2b0b  ldc.i4.2
0x2b0c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, valuetype [mscorlib]Microsoft.Win32.RegistryKeyPermissionCheck)
0x2b11  stloc.0
0x2b12  ldloc.0
0x2b13  brtrue.s loc_2B17
0x2b15  ldnull
0x2b16  ret
0x2b17  ldloc.2
0x2b18  ldc.i4.1
0x2b19  add
0x2b1a  stloc.2
0x2b1b  ldloc.2
0x2b1c  ldloc.1
0x2b1d  ldlen
0x2b1e  conv.i4
0x2b1f  blt.s    loc_2B05
0x2b21  ldloc.0
0x2b22  ret
```
