# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::.ctor

- ea: `0xa6a0`
- end: `0xa6f7`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::.ctor`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7ad0`

## callees

- `0xa4f0`
- `0xa640`

## string_xrefs

- `0xa6db`: `xmlns`
- `0xa6c4`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xa6a0  ldarg.0
0xa6a1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::.ctor()
0xa6a6  ldarg.0
0xa6a7  ldarg.1
0xa6a8  stfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa6ad  ldarg.0
0xa6ae  ldarg.3
0xa6af  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_TextBoxTypes
0xa6b4  ldarg.0
0xa6b5  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xa6ba  ldstr    aXsd// "xsd"
0xa6bf  ldstr    aSchema_0// "schema"
0xa6c4  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2001/XMLSchema"
0xa6c9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xa6ce  ldarg.0
0xa6cf  ldstr    aTargetnamespac// "targetNamespace"
0xa6d4  ldarg.2
0xa6d5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xa6da  ldarg.0
0xa6db  ldstr    aXmlns// "xmlns"
0xa6e0  ldarg.2
0xa6e1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xa6e6  ldarg.0
0xa6e7  ldstr    aElementformdef// "elementFormDefault"
0xa6ec  ldstr    aQualified// "qualified"
0xa6f1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xa6f6  ret
```
