# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCell

- ea: `0x8930`
- end: `0x89d7`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCell`
- size: `167`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x84c0`
- `0x8670`
- `0x8910`

## callees

- `0x8110`
- `0x8130`
- `0x8930`
- `0x9fd0`
- `0xa020`
- `0xa090`
- `0xa110`

## pseudocode

```c

```

## disassembly

```asm
0x8930  ldarg.1
0x8931  brfalse.s loc_893C
0x8933  ldarg.1
0x8934  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_DataElementOutput()
0x8939  ldc.i4.1
0x893a  bne.un.s loc_893E
0x893c  ldc.i4.0
0x893d  ret
0x893e  ldarg.1
0x893f  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_DataElementOutput()
0x8944  ldc.i4.0
0x8945  ceq
0x8947  stloc.0
0x8948  ldloc.0
0x8949  ldarg.3
0x894a  and
0x894b  brfalse.s loc_894F
0x894d  ldc.i4.1
0x894e  ret
0x894f  ldc.i4.0
0x8950  stloc.1
0x8951  ldloc.0
0x8952  brfalse.s loc_89B8
0x8954  ldarg.0
0x8955  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x895a  ldarg.1
0x895b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_DataElementName()
0x8960  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8965  stloc.2
0x8966  ldloc.2
0x8967  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x896c  brfalse.s loc_8980
0x896e  ldarg.0
0x896f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8974  ldarg.1
0x8975  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_ID()
0x897a  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultCellTag(string aCellID)
0x897f  stloc.2
0x8980  ldarg.0
0x8981  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8986  ldloc.2
0x8987  ldarg.s  4
0x8989  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCell(string name, bool firstInstance)
0x898e  ldarg.1
0x898f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_CellContents()
0x8994  brfalse.s loc_89A9
0x8996  ldarg.0
0x8997  ldarg.1
0x8998  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_CellContents()
0x899d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x89a2  ldarg.s  4
0x89a4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool firstInstance)
0x89a9  ldarg.0
0x89aa  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x89af  ldarg.s  4
0x89b1  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x89b6  br.s     loc_89D5
0x89b8  ldarg.1
0x89b9  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_CellContents()
0x89be  brfalse.s loc_89D5
0x89c0  ldarg.0
0x89c1  ldarg.1
0x89c2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell::get_CellContents()
0x89c7  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x89cc  ldarg.3
0x89cd  ldarg.s  4
0x89cf  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x89d4  stloc.1
0x89d5  ldloc.1
0x89d6  ret
```
