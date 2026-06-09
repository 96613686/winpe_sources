# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::CreateServiceDocument

- ea: `0x2be0`
- end: `0x2c7e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentVisitor::CreateServiceDocument`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1cf0`

## callees

- `0x2b80`
- `0x2be0`

## string_xrefs

- `0x2be6`: `service`
- `0x2bfb`: `xmlns`
- `0x2c16`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldarg.0
0x2be1  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2be6  ldstr    aService// "service"
0x2beb  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2007/app"
0x2bf0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x2bf5  ldarg.0
0x2bf6  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2bfb  ldstr    aXmlns// "xmlns"
0x2c00  ldstr    aAtom// "atom"
0x2c05  ldnull
0x2c06  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2005/Atom"
0x2c0b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x2c10  ldarg.0
0x2c11  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2c16  ldstr    aXmlns// "xmlns"
0x2c1b  ldstr    aApp// "app"
0x2c20  ldnull
0x2c21  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2007/app"
0x2c26  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x2c2b  ldarg.0
0x2c2c  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2c31  ldstr    aWorkspace// "workspace"
0x2c36  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2c3b  ldarg.0
0x2c3c  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_xmlWriter
0x2c41  ldstr    aTitle// "title"
0x2c46  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2005/Atom"
0x2c4b  ldarg.1
0x2c4c  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x2c51  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c56  brtrue.s loc_2C60
0x2c58  ldarg.1
0x2c59  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x2c5e  br.s     loc_2C65
0x2c60  ldstr    aDefault// "Default"
0x2c65  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0x2c6a  ldarg.0
0x2c6b  ldarg.0
0x2c6c  ldarg.1
0x2c6d  ldarg.0
0x2c6e  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::m_reportServerParameters
0x2c73  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::BuildBaseUrl(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report report, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x2c78  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::m_baseUrl
0x2c7d  ret
```
