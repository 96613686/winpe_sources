# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangle

- ea: `0x8030`
- end: `0x8078`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkRectangle`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x8030`
- `0x8080`
- `0x9fe0`
- `0xa020`
- `0xa090`
- `0xa130`

## pseudocode

```c

```

## disassembly

```asm
0x8030  ldarg.0
0x8031  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8036  ldarg.1
0x8037  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x803c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8041  stloc.0
0x8042  ldloc.0
0x8043  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8048  brfalse.s loc_8056
0x804a  ldarg.0
0x804b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8050  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultRectangleTag()
0x8055  stloc.0
0x8056  ldarg.0
0x8057  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x805c  ldloc.0
0x805d  ldarg.2
0x805e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartRectangle(string name, bool firstInstance)
0x8063  ldarg.0
0x8064  ldarg.1
0x8065  ldarg.2
0x8066  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelRectangleContents(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rect, bool firstInstance)
0x806b  ldarg.0
0x806c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8071  ldarg.2
0x8072  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8077  ret
```
