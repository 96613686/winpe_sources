# Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteNamespacePrefix

- ea: `0xb420`
- end: `0xb438`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteNamespacePrefix`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb400`
- `0xb440`
- `0xb720`

## string_xrefs

- `0xb42c`: `http://www.w3.org/2000/xmlns/`
- `0xb426`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0xb420  ldarg.0
0xb421  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Modeling.ModelingXmlWriter::m_xw
0xb426  ldstr    aXmlns// "xmlns"
0xb42b  ldarg.1
0xb42c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xb431  ldarg.2
0xb432  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb437  ret
```
