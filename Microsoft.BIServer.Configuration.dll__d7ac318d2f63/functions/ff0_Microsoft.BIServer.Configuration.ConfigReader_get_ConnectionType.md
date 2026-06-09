# Microsoft.BIServer.Configuration.ConfigReader::get_ConnectionType

- ea: `0xff0`
- end: `0x1010`
- name: `Microsoft.BIServer.Configuration.ConfigReader::get_ConnectionType`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x67f0`

## callees

- `0x15d0`

## pseudocode

```c

```

## disassembly

```asm
0xff0  ldtoken  Microsoft.BIServer.Configuration.CatalogConnectionType
0xff5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xffa  ldarg.0
0xffb  ldstr    aConnectiontype// "ConnectionType"
0x1000  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadString(string fieldName)
0x1005  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x100a  unbox.any Microsoft.BIServer.Configuration.CatalogConnectionType
0x100f  ret
```
