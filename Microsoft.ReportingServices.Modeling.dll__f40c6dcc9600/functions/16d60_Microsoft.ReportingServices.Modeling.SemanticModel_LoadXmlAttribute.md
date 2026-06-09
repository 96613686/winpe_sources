# Microsoft.ReportingServices.Modeling.SemanticModel::LoadXmlAttribute

- ea: `0x16d60`
- end: `0x16d88`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::LoadXmlAttribute`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8000`
- `0xa7c0`
- `0x13ee0`
- `0x16d60`

## string_xrefs

- `0x16d66`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0x16d60  ldarg.1
0x16d61  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x16d66  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x16d6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16d70  brfalse.s loc_16D80
0x16d72  ldarg.0
0x16d73  ldfld    class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticModel::m_namespacePrefixes
0x16d78  ldarg.1
0x16d79  callvirt instance void Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::AddFromReader(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x16d7e  ldc.i4.1
0x16d7f  ret
0x16d80  ldarg.0
0x16d81  ldarg.1
0x16d82  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::LoadXmlAttribute(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x16d87  ret
```
