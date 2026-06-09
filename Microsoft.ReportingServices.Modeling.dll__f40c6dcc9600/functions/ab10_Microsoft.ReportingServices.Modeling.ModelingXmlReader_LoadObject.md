# Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject

- ea: `0xab10`
- end: `0xab1f`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject`
- size: `15`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8ec0`
- `0x11770`
- `0x11f70`
- `0x12500`
- `0x13eb0`
- `0x1ef60`
- `0x21a10`
- `0x21d80`
- `0x22350`
- `0x228d0`
- `0x22c00`
- `0x23480`
- `0x27ef0`
- `0x2a5a0`
- `0x2a8f0`
- `0x2bf00`
- `0x37a50`
- `0x37ba0`
- `0x37eb0`
- `0x37f60`
- `0x38060`

## callees

- `0xab20`
- `0xae40`

## pseudocode

```c

```

## disassembly

```asm
0xab10  ldarg.0
0xab11  ldarg.1
0xab12  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::CheckElement(string name)
0xab17  ldarg.0
0xab18  ldarg.2
0xab19  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0xab1e  ret
```
