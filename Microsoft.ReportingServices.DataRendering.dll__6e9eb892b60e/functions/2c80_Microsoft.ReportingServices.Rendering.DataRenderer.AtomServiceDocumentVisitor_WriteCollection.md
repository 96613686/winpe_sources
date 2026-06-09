# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::WriteCollection

- ea: `0x2c80`
- end: `0x2ce0`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::WriteCollection`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2c8c`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x2c80  ldarg.0
0x2c81  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::m_baseUrl
0x2c86  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(string)
0x2c8b  dup
0x2c8c  ldstr    aItempath// "ItemPath"
0x2c91  ldarg.3
0x2c92  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendRenderingParameter(string, string)
0x2c97  callvirt instance string [mscorlib]System.Object::ToString()
0x2c9c  stloc.0
0x2c9d  ldarg.0
0x2c9e  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2ca3  ldstr    aCollection// "collection"
0x2ca8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2cad  ldarg.0
0x2cae  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2cb3  ldstr    aHref// "href"
0x2cb8  ldloc.0
0x2cb9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x2cbe  ldarg.0
0x2cbf  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2cc4  ldstr    aTitle// "title"
0x2cc9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2005/Atom"
0x2cce  ldarg.2
0x2ccf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0x2cd4  ldarg.0
0x2cd5  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2cda  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2cdf  ret
```
