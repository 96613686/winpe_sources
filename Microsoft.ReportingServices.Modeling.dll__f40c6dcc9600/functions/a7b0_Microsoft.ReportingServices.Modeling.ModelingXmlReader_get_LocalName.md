# Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName

- ea: `0xa7b0`
- end: `0xa7bc`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName`
- size: `12`
- prototype: ``
- caller_count: `78`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8000`
- `0x8ef0`
- `0xf4b0`
- `0x10d00`
- `0x117f0`
- `0x11d30`
- `0x12010`
- `0x12300`
- `0x12620`
- `0x12ca0`
- `0x13250`
- `0x13530`
- `0x13ee0`
- `0x13f10`
- `0x149b0`
- `0x14ed0`
- `0x15620`
- `0x16520`
- `0x16d90`
- `0x18040`
- `0x18d40`
- `0x18d70`
- `0x1a530`
- `0x1b460`
- `0x1bc00`
- `0x1c100`
- `0x1d330`
- `0x1e1a0`
- `0x1ef80`
- `0x21a40`
- `0x21a70`
- `0x21dc0`
- `0x22380`
- `0x22900`
- `0x22c30`
- `0x22c60`
- `0x234f0`
- `0x26080`
- `0x26ef0`
- `0x26f30`
- `0x27150`
- `0x27190`
- `0x27560`
- `0x27600`
- `0x27c80`
- `0x280e0`
- `0x28120`
- `0x29f40`
- `0x29f80`
- `0x2a400`

## pseudocode

```c

```

## disassembly

```asm
0xa7b0  ldarg.0
0xa7b1  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xa7b6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa7bb  ret
```
