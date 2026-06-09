# Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString

- ea: `0xaa40`
- end: `0xaa73`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString`
- size: `51`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa8f0`
- `0xa960`
- `0xaa80`
- `0xaa90`
- `0xaed0`
- `0xc0b0`
- `0xc470`
- `0xc930`
- `0xf4b0`
- `0x10d00`
- `0x13f10`
- `0x16d90`
- `0x18d40`
- `0x1a530`
- `0x1d330`
- `0x21a40`
- `0x22c30`
- `0x27600`
- `0x27c80`
- `0x2a400`
- `0x2a5c0`
- `0x2a6a0`
- `0x2a910`
- `0x2ac10`
- `0x34010`
- `0x34f60`
- `0x37040`

## callees

- `0xaa40`

## pseudocode

```c

```

## disassembly

```asm
0xaa40  ldarg.0
0xaa41  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xaa46  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaa4b  ldc.i4.1
0xaa4c  bne.un.s loc_AA5C
0xaa4e  ldarg.0
0xaa4f  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xaa54  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0xaa59  stloc.0
0xaa5a  br.s     loc_AA68
0xaa5c  ldarg.0
0xaa5d  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::m_xr
0xaa62  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0xaa67  stloc.0
0xaa68  ldloc.0
0xaa69  dup
0xaa6a  brtrue.s loc_AA72
0xaa6c  pop
0xaa6d  ldsfld   string [mscorlib]System.String::Empty
0xaa72  ret
```
