# Microsoft.ReportingServices.Modeling.SemanticQuery::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlAttribute

- ea: `0x234c0`
- end: `0x234e2`
- name: `Microsoft.ReportingServices.Modeling.SemanticQuery::Microsoft.ReportingServices.Modeling.IXmlLoadable.LoadXmlAttribute`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8000`
- `0xa7c0`
- `0x234c0`

## string_xrefs

- `0x234c6`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x234c0  ldarg.1
0x234c1  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x234c6  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x234cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x234d0  brfalse.s loc_234E0
0x234d2  ldarg.0
0x234d3  ldfld    class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_namespacePrefixes
0x234d8  ldarg.1
0x234d9  callvirt instance void Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::AddFromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x234de  ldc.i4.1
0x234df  ret
0x234e0  ldc.i4.0
0x234e1  ret
```
