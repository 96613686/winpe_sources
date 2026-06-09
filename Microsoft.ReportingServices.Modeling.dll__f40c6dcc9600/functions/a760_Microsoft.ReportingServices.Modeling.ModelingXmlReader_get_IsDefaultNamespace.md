# Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace

- ea: `0xa760`
- end: `0xa7a9`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace`
- size: `73`
- prototype: ``
- caller_count: `71`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

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
- `0x26ef0`
- `0x26f30`
- `0x27150`
- `0x27600`
- `0x27c80`
- `0x280e0`
- `0x28120`
- `0x29f40`
- `0x29f80`
- `0x2a400`
- `0x2a5c0`
- `0x2a6a0`
- `0x2a910`
- `0x2a980`
- `0x2ac10`

## callees

- `0xa760`

## pseudocode

```c

```

## disassembly

```asm
0xa760  ldarg.0
0xa761  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xa766  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa76b  ldc.i4.1
0xa76c  bne.un.s loc_A785
0xa76e  ldarg.0
0xa76f  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xa774  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa779  ldarg.0
0xa77a  ldfld    string Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_defaultNamespace
0xa77f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa784  ret
0xa785  ldarg.0
0xa786  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xa78b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa790  ldc.i4.2
0xa791  bne.un.s loc_A7A7
0xa793  ldarg.0
0xa794  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xa799  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa79e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa7a3  ldc.i4.0
0xa7a4  ceq
0xa7a6  ret
0xa7a7  ldc.i4.0
0xa7a8  ret
```
