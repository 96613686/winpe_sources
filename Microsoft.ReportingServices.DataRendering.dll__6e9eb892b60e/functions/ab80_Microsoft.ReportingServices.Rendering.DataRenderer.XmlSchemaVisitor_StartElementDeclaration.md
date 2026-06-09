# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartElementDeclaration

- ea: `0xab80`
- end: `0xabf5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartElementDeclaration`
- size: `117`
- prototype: ``
- caller_count: `13`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa9a0`
- `0xa9b0`
- `0xa9c0`
- `0xa9d0`
- `0xa9e0`
- `0xa9f0`
- `0xaa10`
- `0xaa20`
- `0xaa30`
- `0xaa40`
- `0xaa60`
- `0xaa70`
- `0xaa90`

## callees

- `0xa2f0`
- `0xa4f0`
- `0xab50`
- `0xab80`
- `0xad00`
- `0xad80`

## string_xrefs

- `0xabb2`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xab80  ldarg.0
0xab81  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartComplex()
0xab86  ldarg.0
0xab87  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartSequence()
0xab8c  ldarg.0
0xab8d  ldarg.0
0xab8e  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xab93  ldc.i4.1
0xab94  add
0xab95  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xab9a  ldarg.0
0xab9b  ldarga.s 1
0xab9d  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::ValidateElement(string& name)
0xaba2  ldarg.0
0xaba3  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xaba8  ldstr    aXsd// "xsd"
0xabad  ldstr    aElement// "element"
0xabb2  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2001/XMLSchema"
0xabb7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xabbc  ldarg.0
0xabbd  ldstr    aName_0// "name"
0xabc2  ldarg.1
0xabc3  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xabc8  ldarg.2
0xabc9  ldc.i4.1
0xabca  beq.s    loc_ABDE
0xabcc  ldarg.0
0xabcd  ldstr    aMinoccurs// "minOccurs"
0xabd2  ldarg.0
0xabd3  ldarg.2
0xabd4  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::Cardinality2String(valuetype Cardinality cardinality)
0xabd9  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xabde  ldarg.3
0xabdf  ldc.i4.1
0xabe0  beq.s    loc_ABF4
0xabe2  ldarg.0
0xabe3  ldstr    aMaxoccurs// "maxOccurs"
0xabe8  ldarg.0
0xabe9  ldarg.3
0xabea  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::Cardinality2String(valuetype Cardinality cardinality)
0xabef  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::WriteAttributeString(string localName, string value)
0xabf4  ret
```
