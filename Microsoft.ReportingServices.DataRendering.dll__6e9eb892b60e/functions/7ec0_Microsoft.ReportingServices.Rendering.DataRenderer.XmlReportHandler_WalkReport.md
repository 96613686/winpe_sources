# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReport

- ea: `0x7ec0`
- end: `0x7f85`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReport`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7eb0`
- `0x9c60`

## callees

- `0x7ec0`
- `0x7f90`
- `0x9f60`
- `0x9f70`
- `0xa020`
- `0xa040`
- `0xa090`
- `0xa0b0`
- `0xa0c0`

## pseudocode

```c

```

## disassembly

```asm
0x7ec0  ldarg.0
0x7ec1  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x7ec6  stloc.0
0x7ec7  ldarg.0
0x7ec8  ldarg.1
0x7ec9  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x7ece  ldarg.0
0x7ecf  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7ed4  ldarg.1
0x7ed5  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementName()
0x7eda  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x7edf  stloc.1
0x7ee0  ldloc.1
0x7ee1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ee6  brfalse.s loc_7EF4
0x7ee8  ldarg.0
0x7ee9  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7eee  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultReportTag()
0x7ef3  stloc.1
0x7ef4  ldarg.2
0x7ef5  brfalse.s loc_7F05
0x7ef7  ldarg.0
0x7ef8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7efd  ldloc.1
0x7efe  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartRootReport(string name)
0x7f03  br.s     loc_7F12
0x7f05  ldarg.0
0x7f06  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7f0b  ldloc.1
0x7f0c  ldarg.3
0x7f0d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartReport(string name, bool firstInstance)
0x7f12  ldarg.0
0x7f13  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7f18  ldarg.0
0x7f19  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7f1e  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getXmlRdlNameTag()
0x7f23  ldarg.1
0x7f24  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_Name()
0x7f29  ldc.i4.s 0x12
0x7f2b  ldarg.3
0x7f2c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x7f31  ldarg.1
0x7f32  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x7f37  brfalse.s loc_7F71
0x7f39  ldarg.1
0x7f3a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x7f3f  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Count()
0x7f44  ldc.i4.0
0x7f45  ble.s    loc_7F71
0x7f47  ldc.i4.0
0x7f48  stloc.2
0x7f49  br.s     loc_7F63
0x7f4b  ldarg.0
0x7f4c  ldarg.1
0x7f4d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x7f52  ldloc.2
0x7f53  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Item(!!T0)
0x7f58  ldloc.2
0x7f59  ldarg.3
0x7f5a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportSection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection section, int32 index, bool firstInstance)
0x7f5f  ldloc.2
0x7f60  ldc.i4.1
0x7f61  add
0x7f62  stloc.2
0x7f63  ldloc.2
0x7f64  ldarg.1
0x7f65  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSectionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_ReportSections()
0x7f6a  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportSection>::get_Count()
0x7f6f  blt.s    loc_7F4B
0x7f71  ldarg.0
0x7f72  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x7f77  ldarg.3
0x7f78  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x7f7d  ldarg.0
0x7f7e  ldloc.0
0x7f7f  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x7f84  ret
```
