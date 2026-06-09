# Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::CreateCSDLDocument

- ea: `0x2d30`
- end: `0x2dcd`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::CreateCSDLDocument`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1e90`

## callees

- `0x2d20`

## string_xrefs

- `0x2da1`: `xmlns`
- `0x2d52`: `http://schemas.microsoft.com/ado/2007/06/edmx`
- `0x2d7c`: `http://schemas.microsoft.com/ado/2007/06/edmx`
- `0x2d77`: `DataServices`
- `0x2d91`: `http://schemas.microsoft.com/ado/2006/04/edm`
- `0x2dac`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/feedmetadata`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldarg.0
0x2d31  ldarg.1
0x2d32  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::m_report
0x2d37  ldarg.0
0x2d38  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2d3d  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::m_entityTypes
0x2d42  ldarg.0
0x2d43  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2d48  ldstr    aEdmx// "edmx"
0x2d4d  ldstr    aEdmx_0// "Edmx"
0x2d52  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/ado/2007/0"...
0x2d57  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x2d5c  ldarg.0
0x2d5d  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2d62  ldstr    aVersion// "Version"
0x2d67  ldstr    a10// "1.0"
0x2d6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2d71  ldarg.0
0x2d72  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2d77  ldstr    aDataservices// "DataServices"
0x2d7c  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/ado/2007/0"...
0x2d81  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x2d86  ldarg.0
0x2d87  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2d8c  ldstr    aSchema// "Schema"
0x2d91  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/ado/2006/0"...
0x2d96  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x2d9b  ldarg.0
0x2d9c  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2da1  ldstr    aXmlns// "xmlns"
0x2da6  ldstr    aRs// "rs"
0x2dab  ldnull
0x2dac  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x2db1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x2db6  ldarg.0
0x2db7  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2dbc  ldstr    aNamespace// "Namespace"
0x2dc1  ldarg.0
0x2dc2  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.AtomCSDLSchemaVisitor::get_SchemaNamespace()
0x2dc7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2dcc  ret
```
