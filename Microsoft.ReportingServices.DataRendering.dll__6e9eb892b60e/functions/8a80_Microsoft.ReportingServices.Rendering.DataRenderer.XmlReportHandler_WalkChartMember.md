# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMember

- ea: `0x8a80`
- end: `0x8cae`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMember`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8a50`

## callees

- `0x8a50`
- `0x8a80`
- `0x8cb0`
- `0x8d30`
- `0x9fa0`
- `0x9ff0`
- `0xa020`
- `0xa070`
- `0xa090`
- `0xa160`
- `0xa190`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  ldarg.1
0x8a81  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_DataElementOutput()
0x8a86  ldc.i4.1
0x8a87  bne.un.s loc_8A8A
0x8a89  ret
0x8a8a  ldnull
0x8a8b  stloc.0
0x8a8c  ldc.i4.1
0x8a8d  stloc.1
0x8a8e  ldc.i4.1
0x8a8f  stloc.2
0x8a90  ldarg.1
0x8a91  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x8a96  brtrue.s loc_8AD5
0x8a98  ldarg.1
0x8a99  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Instance()
0x8a9e  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance
0x8aa3  stloc.0
0x8aa4  ldloc.0
0x8aa5  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance::ResetContext()
0x8aaa  ldloc.0
0x8aab  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance::MoveNext()
0x8ab0  stloc.1
0x8ab1  ldarg.2
0x8ab2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x8ab7  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartInstance
0x8abc  stloc.s  7
0x8abe  ldarg.0
0x8abf  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8ac4  ldloc.s  7
0x8ac6  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionInstance::get_NoRows()
0x8acb  callvirt instance valuetype Microsoft.ReportingServices.Rendering.DataRenderer.RowCount Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::Count(bool noRows)
0x8ad0  stloc.2
0x8ad1  ldloc.2
0x8ad2  brtrue.s loc_8AD5
0x8ad4  ret
0x8ad5  ldarg.0
0x8ad6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8adb  ldarg.1
0x8adc  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_DataElementName()
0x8ae1  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8ae6  stloc.3
0x8ae7  ldloc.3
0x8ae8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8aed  brfalse.s loc_8B16
0x8aef  ldarg.1
0x8af0  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x8af5  brfalse.s loc_8B16
0x8af7  ldarg.1
0x8af8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Label()
0x8afd  brfalse.s loc_8B16
0x8aff  ldarg.0
0x8b00  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8b05  ldarg.1
0x8b06  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Label()
0x8b0b  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty::get_Value()
0x8b10  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8b15  stloc.3
0x8b16  ldloc.3
0x8b17  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8b1c  brfalse.s loc_8B3C
0x8b1e  ldarg.0
0x8b1f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8b24  ldarg.1
0x8b25  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x8b2a  ldarg.3
0x8b2b  ldarg.3
0x8b2c  ldind.i4
0x8b2d  stloc.s  8
0x8b2f  ldloc.s  8
0x8b31  ldc.i4.1
0x8b32  add
0x8b33  stind.i4
0x8b34  ldloc.s  8
0x8b36  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultChartMemberTag(bool isCategory, int32 aCellIndex)
0x8b3b  stloc.3
0x8b3c  ldarg.0
0x8b3d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8b42  ldloc.3
0x8b43  ldc.i4.1
0x8b44  ldarg.s  4
0x8b46  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartChartMember(string name, bool isStatic, bool firstInstance)
0x8b4b  ldc.i4.0
0x8b4c  stloc.s  4
0x8b4e  ldc.i4.1
0x8b4f  stloc.s  5
0x8b51  ldarg.s  4
0x8b53  stloc.s  6
0x8b55  br       loc_8C9A
0x8b5a  ldarg.1
0x8b5b  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x8b60  brtrue   loc_8C16
0x8b65  ldarg.0
0x8b66  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8b6b  ldarg.1
0x8b6c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8b71  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_DataElementName()
0x8b76  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8b7b  stloc.s  9
0x8b7d  ldloc.s  9
0x8b7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8b84  brfalse.s loc_8C00
0x8b86  ldarg.1
0x8b87  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8b8c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GroupExpressionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_GroupExpressions()
0x8b91  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty>::get_Count()
0x8b96  ldc.i4.0
0x8b97  ble.s    loc_8BDD
0x8b99  ldarg.1
0x8b9a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8b9f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GroupExpressionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_GroupExpressions()
0x8ba4  ldc.i4.0
0x8ba5  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty>::get_Item(!!T0)
0x8baa  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty::get_Value()
0x8baf  stloc.s  0xA
0x8bb1  ldloc.s  0xA
0x8bb3  brfalse.s loc_8BDD
0x8bb5  ldarg.0
0x8bb6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8bbb  ldarg.1
0x8bbc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_Group()
0x8bc1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GroupExpressionCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Group::get_GroupExpressions()
0x8bc6  ldc.i4.0
0x8bc7  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty>::get_Item(!!T0)
0x8bcc  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty::get_Value()
0x8bd1  callvirt instance string [mscorlib]System.Object::ToString()
0x8bd6  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8bdb  stloc.s  9
0x8bdd  ldloc.s  9
0x8bdf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8be4  brfalse.s loc_8C00
0x8be6  ldarg.0
0x8be7  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8bec  ldarg.1
0x8bed  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x8bf2  ldloc.s  4
0x8bf4  dup
0x8bf5  ldc.i4.1
0x8bf6  add
0x8bf7  stloc.s  4
0x8bf9  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultChartCollectionTag(bool isCategory, int32 aIndex)
0x8bfe  stloc.s  9
0x8c00  ldarg.s  4
0x8c02  ldloc.s  5
0x8c04  and
0x8c05  stloc.s  6
0x8c07  ldarg.0
0x8c08  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8c0d  ldloc.s  9
0x8c0f  ldloc.s  6
0x8c11  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x8c16  ldarg.1
0x8c17  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Children()
0x8c1c  brfalse.s loc_8C38
0x8c1e  ldarg.0
0x8c1f  ldarg.1
0x8c20  ldloc.s  6
0x8c22  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool firstInstance)
0x8c27  ldarg.0
0x8c28  ldarg.1
0x8c29  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Children()
0x8c2e  ldarg.2
0x8c2f  ldloc.s  6
0x8c31  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection chartMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool firstInstance)
0x8c36  br.s     loc_8C70
0x8c38  ldarg.1
0x8c39  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_IsCategory()
0x8c3e  brtrue.s loc_8C66
0x8c40  ldarg.0
0x8c41  ldarg.1
0x8c42  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentSeries
0x8c47  ldarg.0
0x8c48  ldarg.1
0x8c49  ldloc.s  6
0x8c4b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool firstInstance)
0x8c50  ldarg.0
0x8c51  ldarg.2
0x8c52  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartHierarchy [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_CategoryHierarchy()
0x8c57  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartHierarchy::get_MemberCollection()
0x8c5c  ldarg.2
0x8c5d  ldloc.s  6
0x8c5f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberCollection chartMemberCollection, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool firstInstance)
0x8c64  br.s     loc_8C70
0x8c66  ldarg.0
0x8c67  ldarg.1
0x8c68  ldarg.2
0x8c69  ldloc.s  6
0x8c6b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartCategoryDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool firstInstance)
0x8c70  ldarg.1
0x8c71  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_IsStatic()
0x8c76  brfalse.s loc_8C7C
0x8c78  ldc.i4.0
0x8c79  stloc.1
0x8c7a  br.s     loc_8C97
0x8c7c  ldarg.0
0x8c7d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8c82  ldloc.s  6
0x8c84  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8c89  ldloc.2
0x8c8a  ldc.i4.2
0x8c8b  bne.un.s loc_8C95
0x8c8d  ldloc.0
0x8c8e  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDynamicMemberInstance::MoveNext()
0x8c93  br.s     loc_8C96
0x8c95  ldc.i4.0
0x8c96  stloc.1
0x8c97  ldc.i4.0
0x8c98  stloc.s  5
0x8c9a  ldloc.1
0x8c9b  brtrue   loc_8B5A
0x8ca0  ldarg.0
0x8ca1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8ca6  ldarg.s  4
0x8ca8  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8cad  ret
```
