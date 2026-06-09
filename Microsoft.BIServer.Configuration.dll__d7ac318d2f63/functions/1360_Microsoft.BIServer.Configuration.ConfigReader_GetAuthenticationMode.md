# Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationMode

- ea: `0x1360`
- end: `0x13a1`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationMode`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x1360`
- `0x1980`
- `0x3c40`

## pseudocode

```c

```

## disassembly

```asm
0x1360  ldtoken  Microsoft.BIServer.Configuration.AuthenticationType
0x1365  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x136a  ldarg.0
0x136b  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1370  callvirt instance string Microsoft.BIServer.Configuration.WebConfigFile::GetAuthenticationType()
0x1375  ldc.i4.1
0x1376  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x137b  unbox.any Microsoft.BIServer.Configuration.AuthenticationType
0x1380  stloc.0
0x1381  ldloc.0
0x1382  brtrue.s loc_139F
0x1384  ldarg.0
0x1385  call     instance valuetype Microsoft.BIServer.Configuration.AuthenticationTypes Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationTypes()
0x138a  box      Microsoft.BIServer.Configuration.AuthenticationTypes
0x138f  ldc.i4.s 0x40
0x1391  box      Microsoft.BIServer.Configuration.AuthenticationTypes
0x1396  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x139b  brfalse.s loc_139F
0x139d  ldc.i4.6
0x139e  ret
0x139f  ldloc.0
0x13a0  ret
```
