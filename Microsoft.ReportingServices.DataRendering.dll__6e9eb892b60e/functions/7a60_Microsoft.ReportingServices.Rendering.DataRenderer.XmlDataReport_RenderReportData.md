# Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderReportData

- ea: `0x7a60`
- end: `0x7aca`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::RenderReportData`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x78f0`

## callees

- `0x7a60`
- `0x7e80`
- `0x7eb0`
- `0xaf80`
- `0xb3d0`

## pseudocode

```c

```

## disassembly

```asm
0x7a60  ldnull
0x7a61  stloc.0
0x7a62  ldarg.0
0x7a63  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noSchema
0x7a68  brtrue.s loc_7A93
0x7a6a  ldarg.1
0x7a6b  ldc.i4.0
0x7a6c  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::GetReportUrl(bool)
0x7a71  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor(string)
0x7a76  dup
0x7a77  ldarg.2
0x7a78  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendCatalogParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x7a7d  dup
0x7a7e  ldstr    aSchema// "Schema"
0x7a83  ldsfld   string [mscorlib]System.Boolean::TrueString
0x7a88  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::AppendRenderingParameter(string, string)
0x7a8d  callvirt instance string [mscorlib]System.Object::ToString()
0x7a92  stloc.0
0x7a93  ldarg.0
0x7a94  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_noNamespace
0x7a99  brfalse.s loc_7AA2
0x7a9b  ldarg.0
0x7a9c  ldnull
0x7a9d  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_schemaName
0x7aa2  ldarg.3
0x7aa3  ldarg.0
0x7aa4  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_schemaName
0x7aa9  ldloc.0
0x7aaa  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xw, string schemaName, string schemaLocation)
0x7aaf  stloc.1
0x7ab0  ldarg.1
0x7ab1  ldloc.1
0x7ab2  ldarg.0
0x7ab3  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataReport::m_useFormattedValues
0x7ab8  ldc.i4.1
0x7ab9  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::.ctor(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report aReport, class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor aXmlVisitor, bool aUseFormattedValues, bool aDoAttributesPass)
0x7abe  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::ProcessReport()
0x7ac3  ldloc.1
0x7ac4  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlDataVisitor::Flush()
0x7ac9  ret
```
