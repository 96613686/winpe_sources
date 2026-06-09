# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStaticTablixMember

- ea: `0x84c0`
- end: `0x8664`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStaticTablixMember`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8460`

## callees

- `0x8110`
- `0x8130`
- `0x8440`
- `0x8460`
- `0x84c0`
- `0x8910`
- `0x8930`
- `0x9fb0`
- `0xa020`
- `0xa090`
- `0xa120`

## pseudocode

```c

```

## disassembly

```asm
0x84c0  ldarg.1
0x84c1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementOutput()
0x84c6  ldc.i4.1
0x84c7  bne.un.s loc_84CB
0x84c9  ldc.i4.0
0x84ca  ret
0x84cb  ldc.i4.0
0x84cc  stloc.0
0x84cd  ldarg.1
0x84ce  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementOutput()
0x84d3  ldc.i4.0
0x84d4  ceq
0x84d6  stloc.1
0x84d7  ldloc.1
0x84d8  brfalse.s loc_8525
0x84da  ldarg.3
0x84db  brfalse.s loc_84DF
0x84dd  ldc.i4.1
0x84de  ret
0x84df  ldarg.0
0x84e0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x84e5  ldarg.1
0x84e6  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementName()
0x84eb  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x84f0  stloc.2
0x84f1  ldloc.2
0x84f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x84f7  brfalse.s loc_8516
0x84f9  ldarg.0
0x84fa  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x84ff  ldarg.1
0x8500  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x8505  ldarg.s  4
0x8507  ldarg.s  4
0x8509  ldind.i4
0x850a  stloc.3
0x850b  ldloc.3
0x850c  ldc.i4.1
0x850d  add
0x850e  stind.i4
0x850f  ldloc.3
0x8510  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultTablixStaticMemberTag(bool isColumn, int32 aCellIndex)
0x8515  stloc.2
0x8516  ldarg.0
0x8517  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x851c  ldloc.2
0x851d  ldc.i4.1
0x851e  ldarg.s  5
0x8520  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartTablixMember(string name, bool isStatic, bool firstInstance)
0x8525  ldarg.1
0x8526  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x852b  brfalse.s loc_8573
0x852d  ldarg.1
0x852e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x8533  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x8538  brfalse.s loc_8573
0x853a  ldloc.1
0x853b  brfalse.s loc_8557
0x853d  ldarg.0
0x853e  ldarg.1
0x853f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x8544  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x8549  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x854e  ldarg.s  5
0x8550  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool firstInstance)
0x8555  br.s     loc_8573
0x8557  ldloc.0
0x8558  ldarg.0
0x8559  ldarg.1
0x855a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x855f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x8564  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x8569  ldarg.3
0x856a  ldarg.s  5
0x856c  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x8571  or
0x8572  stloc.0
0x8573  ldarg.1
0x8574  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x8579  brfalse.s loc_85AA
0x857b  ldloc.1
0x857c  brfalse.s loc_8592
0x857e  ldarg.0
0x857f  ldarg.1
0x8580  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x8585  ldarg.2
0x8586  ldarg.s  5
0x8588  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool firstInstance)
0x858d  br       loc_864F
0x8592  ldloc.0
0x8593  ldarg.0
0x8594  ldarg.1
0x8595  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x859a  ldarg.2
0x859b  ldarg.3
0x859c  ldarg.s  5
0x859e  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x85a3  or
0x85a4  stloc.0
0x85a5  br       loc_864F
0x85aa  ldarg.1
0x85ab  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x85b0  brtrue.s loc_85EC
0x85b2  ldarg.0
0x85b3  ldarg.1
0x85b4  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x85b9  ldloc.1
0x85ba  brfalse.s loc_85D2
0x85bc  ldarg.0
0x85bd  ldarg.2
0x85be  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_ColumnHierarchy()
0x85c3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x85c8  ldarg.2
0x85c9  ldarg.s  5
0x85cb  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool firstInstance)
0x85d0  br.s     loc_864F
0x85d2  ldloc.0
0x85d3  ldarg.0
0x85d4  ldarg.2
0x85d5  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_ColumnHierarchy()
0x85da  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x85df  ldarg.2
0x85e0  ldarg.3
0x85e1  ldarg.s  5
0x85e3  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x85e8  or
0x85e9  stloc.0
0x85ea  br.s     loc_864F
0x85ec  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x85f1  ldarg.0
0x85f2  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x85f7  ldnull
0x85f8  cgt.un
0x85fa  ldstr    aWalkstatictabl// "WalkStaticTablixMember -- CurrentRow =="...
0x85ff  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8604  ldarg.2
0x8605  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x860a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_RowCollection()
0x860f  ldarg.0
0x8610  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x8615  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x861a  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRow>::get_Item(!!T0)
0x861f  ldarg.1
0x8620  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8625  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell>::get_Item(!!T0)
0x862a  stloc.s  4
0x862c  ldloc.s  4
0x862e  brfalse.s loc_864F
0x8630  ldloc.1
0x8631  brfalse.s loc_8640
0x8633  ldarg.0
0x8634  ldloc.s  4
0x8636  ldarg.2
0x8637  ldarg.s  5
0x8639  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aCell, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool firstInstance)
0x863e  br.s     loc_864F
0x8640  ldloc.0
0x8641  ldarg.0
0x8642  ldloc.s  4
0x8644  ldarg.2
0x8645  ldarg.3
0x8646  ldarg.s  5
0x8648  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aCell, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x864d  or
0x864e  stloc.0
0x864f  ldloc.1
0x8650  brfalse.s loc_8662
0x8652  ldarg.3
0x8653  brtrue.s loc_8662
0x8655  ldarg.0
0x8656  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x865b  ldarg.s  5
0x865d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8662  ldloc.0
0x8663  ret
```
