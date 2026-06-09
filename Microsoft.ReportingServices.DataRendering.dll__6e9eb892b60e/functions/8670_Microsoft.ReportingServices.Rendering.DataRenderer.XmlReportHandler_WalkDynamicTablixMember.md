# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkDynamicTablixMember

- ea: `0x8670`
- end: `0x890e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkDynamicTablixMember`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8460`

## callees

- `0x8130`
- `0x8460`
- `0x8670`
- `0x8930`
- `0x9fb0`
- `0x9fc0`
- `0xa020`
- `0xa070`
- `0xa090`
- `0xa0d0`
- `0xa100`

## pseudocode

```c

```

## disassembly

```asm
0x8670  ldarg.1
0x8671  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementOutput()
0x8676  ldc.i4.1
0x8677  bne.un.s loc_867B
0x8679  ldc.i4.0
0x867a  ret
0x867b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8680  ldarg.1
0x8681  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8686  ldnull
0x8687  cgt.un
0x8689  ldstr    aWalkdynamictab// "WalkDynamicTablixMember -- Group == nul"...
0x868e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8693  ldarg.1
0x8694  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Instance()
0x8699  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance
0x869e  stloc.0
0x869f  ldloc.0
0x86a0  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::ResetContext()
0x86a5  ldloc.0
0x86a6  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::MoveNext()
0x86ab  stloc.1
0x86ac  ldarg.2
0x86ad  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x86b2  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixInstance
0x86b7  stloc.2
0x86b8  ldarg.0
0x86b9  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x86be  ldloc.2
0x86bf  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionInstance::get_NoRows()
0x86c4  callvirt instance valuetype Microsoft.ReportingServices.Rendering.DataRenderer.RowCount Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::Count(bool noRows)
0x86c9  stloc.3
0x86ca  ldarg.3
0x86cb  brfalse.s loc_86CF
0x86cd  ldc.i4.1
0x86ce  ret
0x86cf  ldloc.3
0x86d0  brtrue.s loc_86E9
0x86d2  ldarg.0
0x86d3  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x86d8  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor
0x86dd  brtrue.s loc_86E9
0x86df  ldloc.0
0x86e0  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::MoveNext()
0x86e5  brtrue.s loc_86DF
0x86e7  ldc.i4.0
0x86e8  ret
0x86e9  ldarg.0
0x86ea  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x86ef  ldarg.1
0x86f0  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_DataElementName()
0x86f5  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x86fa  stloc.s  4
0x86fc  ldloc.s  4
0x86fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8703  brfalse.s loc_871B
0x8705  ldarg.0
0x8706  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x870b  ldarg.1
0x870c  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x8711  ldarg.s  4
0x8713  ldind.i4
0x8714  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGroupCollectionTag(bool isColumn, int32 aCellIndex)
0x8719  stloc.s  4
0x871b  ldarg.0
0x871c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8721  ldloc.s  4
0x8723  ldarg.s  5
0x8725  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartCollection(string name, bool firstInstance)
0x872a  ldc.i4.1
0x872b  stloc.s  5
0x872d  ldarg.0
0x872e  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8733  isinst   Microsoft.ReportingServices.Rendering.DataRenderer.XmlSchemaVisitor
0x8738  brfalse.s loc_873C
0x873a  ldc.i4.1
0x873b  stloc.1
0x873c  ldarg.1
0x873d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8742  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_DataElementOutput()
0x8747  ldc.i4.1
0x8748  bne.un   loc_88F9
0x874d  ldc.i4.0
0x874e  stloc.1
0x874f  br       loc_88F9
0x8754  ldarg.s  5
0x8756  ldloc.s  5
0x8758  and
0x8759  stloc.s  6
0x875b  ldarg.0
0x875c  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8761  ldarg.1
0x8762  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8767  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_DataElementName()
0x876c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8771  stloc.s  7
0x8773  ldloc.s  7
0x8775  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x877a  brfalse.s loc_8789
0x877c  ldarg.0
0x877d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8782  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGroupDetailTag()
0x8787  stloc.s  7
0x8789  ldarg.0
0x878a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x878f  ldloc.s  7
0x8791  ldc.i4.0
0x8792  ldloc.s  6
0x8794  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartTablixMember(string name, bool isStatic, bool firstInstance)
0x8799  ldc.i4.0
0x879a  stloc.s  8
0x879c  ldarg.1
0x879d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x87a2  brfalse.s loc_87D1
0x87a4  ldarg.1
0x87a5  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x87aa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x87af  brfalse.s loc_87D1
0x87b1  ldarg.0
0x87b2  ldarg.1
0x87b3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x87b8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x87bd  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x87c2  ldarg.0
0x87c3  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x87c8  ldloc.s  6
0x87ca  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x87cf  stloc.s  8
0x87d1  ldc.i4.0
0x87d2  stloc.s  9
0x87d4  ldc.i4.0
0x87d5  stloc.s  0xA
0x87d7  ldc.i4.0
0x87d8  stloc.s  0xB
0x87da  ldnull
0x87db  stloc.s  0xC
0x87dd  ldarg.1
0x87de  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x87e3  brfalse.s loc_87FE
0x87e5  ldarg.0
0x87e6  ldarg.1
0x87e7  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x87ec  ldarg.2
0x87ed  ldarg.0
0x87ee  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x87f3  ldloc.s  6
0x87f5  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x87fa  stloc.s  9
0x87fc  br.s     loc_887D
0x87fe  ldarg.1
0x87ff  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_IsColumn()
0x8804  brtrue.s loc_882B
0x8806  ldarg.0
0x8807  ldarg.1
0x8808  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x880d  ldarg.0
0x880e  ldarg.2
0x880f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_ColumnHierarchy()
0x8814  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x8819  ldarg.2
0x881a  ldarg.0
0x881b  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x8820  ldloc.s  6
0x8822  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x8827  stloc.s  0xA
0x8829  br.s     loc_887D
0x882b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8830  ldarg.0
0x8831  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x8836  ldnull
0x8837  cgt.un
0x8839  ldstr    aWalkstatictabl// "WalkStaticTablixMember -- CurrentRow =="...
0x883e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8843  ldarg.2
0x8844  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_Body()
0x8849  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRowCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixBody::get_RowCollection()
0x884e  ldarg.0
0x884f  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentRow
0x8854  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8859  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixRow>::get_Item(!!T0)
0x885e  ldarg.1
0x885f  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8864  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell>::get_Item(!!T0)
0x8869  stloc.s  0xC
0x886b  ldloc.s  0xC
0x886d  brfalse.s loc_887D
0x886f  ldarg.0
0x8870  ldloc.s  0xC
0x8872  ldarg.2
0x8873  ldc.i4.1
0x8874  ldloc.s  6
0x8876  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aCell, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x887b  stloc.s  0xB
0x887d  ldloc.s  8
0x887f  brfalse.s loc_889B
0x8881  ldarg.0
0x8882  ldarg.1
0x8883  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_TablixHeader()
0x8888  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHeader::get_CellContents()
0x888d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CellContents::get_ReportItem()
0x8892  ldc.i4.0
0x8893  ldloc.s  6
0x8895  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkReportItem(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem ri, bool attributesOnly, bool firstInstance)
0x889a  pop
0x889b  ldloc.s  9
0x889d  brfalse.s loc_88B0
0x889f  ldarg.0
0x88a0  ldarg.1
0x88a1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMember::get_Children()
0x88a6  ldarg.2
0x88a7  ldc.i4.0
0x88a8  ldloc.s  6
0x88aa  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x88af  pop
0x88b0  ldloc.s  0xA
0x88b2  brfalse.s loc_88CA
0x88b4  ldarg.0
0x88b5  ldarg.2
0x88b6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix::get_ColumnHierarchy()
0x88bb  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixHierarchy::get_MemberCollection()
0x88c0  ldarg.2
0x88c1  ldc.i4.0
0x88c2  ldloc.s  6
0x88c4  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixMemberCollection aMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x88c9  pop
0x88ca  ldloc.s  0xB
0x88cc  brfalse.s loc_88DB
0x88ce  ldarg.0
0x88cf  ldloc.s  0xC
0x88d1  ldarg.2
0x88d2  ldc.i4.0
0x88d3  ldloc.s  6
0x88d5  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTablixCell(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixCell aCell, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Tablix aTablix, bool aAttributesOnly, bool firstInstance)
0x88da  pop
0x88db  ldarg.0
0x88dc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x88e1  ldloc.s  6
0x88e3  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x88e8  ldc.i4.0
0x88e9  stloc.s  5
0x88eb  ldloc.3
0x88ec  ldc.i4.2
0x88ed  bne.un.s loc_88F7
0x88ef  ldloc.0
0x88f0  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TablixDynamicMemberInstance::MoveNext()
0x88f5  br.s     loc_88F8
0x88f7  ldc.i4.0
0x88f8  stloc.1
0x88f9  ldloc.1
0x88fa  brtrue   loc_8754
0x88ff  ldarg.0
0x8900  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8905  ldarg.s  5
0x8907  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x890c  ldc.i4.0
0x890d  ret
```
