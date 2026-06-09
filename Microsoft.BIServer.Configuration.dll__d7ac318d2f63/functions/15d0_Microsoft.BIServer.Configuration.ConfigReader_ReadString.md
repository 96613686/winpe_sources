# Microsoft.BIServer.Configuration.ConfigReader::ReadString

- ea: `0x15d0`
- end: `0x15de`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadString`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf30`
- `0xf70`
- `0xfb0`
- `0xff0`
- `0x12f0`
- `0x15b0`
- `0x1bb0`

## callees

- `0x1610`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  ldarg.0
0x15d1  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x15d6  ldarg.1
0x15d7  ldc.i4.0
0x15d8  call     string Microsoft.BIServer.Configuration.ConfigReader::ReadString(class [System.Xml.Linq]System.Xml.Linq.XElement element, string fieldName, [opt] bool elementRequired)
0x15dd  ret
```
