# Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartComplex

- ea: `0xad00`
- end: `0xad3d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::StartComplex`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xab80`
- `0xac30`

## callees

- `0xa420`
- `0xad00`

## string_xrefs

- `0xad2c`: `http://www.w3.org/2001/XMLSchema`
- `0xad27`: `complexType`

## pseudocode

```c

```

## disassembly

```asm
0xad00  ldarg.0
0xad01  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_elementLevel
0xad06  ldarg.0
0xad07  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad0c  beq.s    loc_AD3C
0xad0e  ldarg.0
0xad0f  ldarg.0
0xad10  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad15  ldc.i4.1
0xad16  add
0xad17  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor::m_complexTypeLevel
0xad1c  ldarg.0
0xad1d  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::m_xw
0xad22  ldstr    aXsd// "xsd"
0xad27  ldstr    aComplextype// "complexType"
0xad2c  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2001/XMLSchema"
0xad31  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xad36  ldarg.0
0xad37  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::PushScope()
0xad3c  ret
```
