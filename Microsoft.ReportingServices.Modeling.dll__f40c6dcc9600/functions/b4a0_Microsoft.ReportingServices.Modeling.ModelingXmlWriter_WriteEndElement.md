# Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteEndElement

- ea: `0xb4a0`
- end: `0xb4ac`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteEndElement`
- size: `12`
- prototype: ``
- caller_count: `34`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8f60`
- `0xb4b0`
- `0xb4f0`
- `0xb630`
- `0xb6b0`
- `0xc0f0`
- `0xc4d0`
- `0xc9c0`
- `0x11060`
- `0x11880`
- `0x12060`
- `0x126b0`
- `0x14240`
- `0x15850`
- `0x180d0`
- `0x18140`
- `0x18180`
- `0x181d0`
- `0x18f40`
- `0x1a5b0`
- `0x1b590`
- `0x1bc80`
- `0x1c170`
- `0x1d430`
- `0x1d500`
- `0x1dc40`
- `0x1e1f0`
- `0x1eff0`
- `0x21ad0`
- `0x21e80`
- `0x22440`
- `0x22950`
- `0x22cf0`
- `0x23950`

## pseudocode

```c

```

## disassembly

```asm
0xb4a0  ldarg.0
0xb4a1  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Modeling.ModelingXmlWriter::m_xw
0xb4a6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb4ab  ret
```
