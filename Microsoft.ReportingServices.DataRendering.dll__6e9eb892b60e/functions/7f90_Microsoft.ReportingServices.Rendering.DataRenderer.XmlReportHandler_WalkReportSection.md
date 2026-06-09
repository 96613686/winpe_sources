# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportSection

- ea: `0x7f90`
- end: `0x802c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportSection`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7ec0`

## callees

- `0x7f90`
- `0x80c0`
- `0x9f80`
- `0xa020`
- `0xa090`
- `0xa2c0`

## pseudocode

```c

```

## disassembly

```asm
0x7f90  ldarg.1
0x7f91  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x7f96  brfalse  loc_802B
0x7f9b  ldarg.1
0x7f9c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x7fa1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x7fa6  brfalse  loc_802B
0x7fab  ldarg.1
0x7fac  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_DataElementOutput()
0x7fb1  ldc.i4.2
0x7fb2  bne.un.s loc_7FC7
0x7fb4  ldarg.0
0x7fb5  ldarg.1
0x7fb6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x7fbb  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x7fc0  ldarg.3
0x7fc1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection ric, bool firstInstance)
0x7fc6  ret
0x7fc7  ldarg.1
0x7fc8  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_DataElementOutput()
0x7fcd  brtrue.s loc_802B
0x7fcf  ldarg.0
0x7fd0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7fd5  ldarg.1
0x7fd6  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_DataElementName()
0x7fdb  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x7fe0  stloc.0
0x7fe1  ldloc.0
0x7fe2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7fe7  brfalse.s loc_8000
0x7fe9  ldarg.0
0x7fea  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7fef  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultSectionTag()
0x7ff4  ldarg.1
0x7ff5  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_ID()
0x7ffa  call     string [mscorlib]System.String::Concat(string, string)
0x7fff  stloc.0
0x8000  ldarg.0
0x8001  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8006  ldloc.0
0x8007  ldarg.3
0x8008  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartReportSection(string name, bool firstInstance)
0x800d  ldarg.0
0x800e  ldarg.1
0x800f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection::get_Body()
0x8014  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Body::get_ReportItemCollection()
0x8019  ldarg.3
0x801a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection ric, bool firstInstance)
0x801f  ldarg.0
0x8020  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8025  ldarg.3
0x8026  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x802b  ret
```
