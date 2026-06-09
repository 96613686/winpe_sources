# Microsoft.BIServer.Configuration.ConfigReader::ReadGuid

- ea: `0x15b0`
- end: `0x15cd`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadGuid`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ba0`

## callees

- `0x15b0`
- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0x15b0  ldarg.0
0x15b1  ldarg.1
0x15b2  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0x15b7  stloc.0
0x15b8  ldloc.0
0x15b9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15be  brtrue.s loc_15C7
0x15c0  ldloc.0
0x15c1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x15c6  ret
0x15c7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x15cc  ret
```
