# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartCategoryDetails

- ea: `0x8d30`
- end: `0x8ec6`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartCategoryDetails`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8a80`

## callees

- `0x8cb0`
- `0x8cd0`
- `0x8d30`
- `0x8ed0`
- `0x8f00`
- `0xa000`
- `0xa020`
- `0xa090`
- `0xa170`

## pseudocode

```c

```

## disassembly

```asm
0x8d30  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8d35  ldarg.0
0x8d36  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentSeries
0x8d3b  ldnull
0x8d3c  cgt.un
0x8d3e  ldstr    aWalkchartcateg// "WalkChartCategoryDetails -- m_CurrentSe"...
0x8d43  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8d48  ldarg.2
0x8d49  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_ChartData()
0x8d4e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData::get_SeriesCollection()
0x8d53  ldarg.0
0x8d54  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentSeries
0x8d59  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8d5e  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeries>::get_Item(!!T0)
0x8d63  ldarg.1
0x8d64  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8d69  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint>::get_Item(!!T0)
0x8d6e  stloc.0
0x8d6f  ldloc.0
0x8d70  brtrue.s loc_8D73
0x8d72  ret
0x8d73  ldc.i4.0
0x8d74  stloc.1
0x8d75  ldc.i4.0
0x8d76  stloc.2
0x8d77  ldarg.2
0x8d78  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_DataValueSequenceRendering()
0x8d7d  brfalse.s loc_8DFC
0x8d7f  ldarg.2
0x8d80  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_ChartData()
0x8d85  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData::get_SeriesCollection()
0x8d8a  ldarg.0
0x8d8b  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentSeries
0x8d90  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8d95  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeries>::get_Item(!!T0)
0x8d9a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType> [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeries::get_Type()
0x8d9f  stloc.3
0x8da0  ldarg.2
0x8da1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_ChartData()
0x8da6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartData::get_SeriesCollection()
0x8dab  ldarg.0
0x8dac  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentSeries
0x8db1  callvirt instance int32 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataRegionMember::get_MemberCellIndex()
0x8db6  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeries>::get_Item(!!T0)
0x8dbb  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype> [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeries::get_Subtype()
0x8dc0  stloc.s  4
0x8dc2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8dc7  ldloc.3
0x8dc8  ldnull
0x8dc9  cgt.un
0x8dcb  ldstr    aWalkchartcateg_0// "WalkChartCategoryDetails: for an old re"...
0x8dd0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8dd5  ldloc.3
0x8dd6  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType>::get_Value()
0x8ddb  stloc.1
0x8ddc  ldloc.1
0x8ddd  ldc.i4.6
0x8dde  bne.un.s loc_8DFC
0x8de0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8de5  ldloc.s  4
0x8de7  ldnull
0x8de8  cgt.un
0x8dea  ldstr    aWalkchartcateg_1// "WalkChartCategoryDetails: for an old re"...
0x8def  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8df4  ldloc.s  4
0x8df6  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype>::get_Value()
0x8dfb  stloc.2
0x8dfc  ldloc.0
0x8dfd  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint::get_DataElementOutput()
0x8e02  stloc.s  7
0x8e04  ldloc.s  7
0x8e06  switch   loc_8E21, loc_8E18, loc_8E7D
0x8e17  ret
0x8e18  ldarg.0
0x8e19  ldarg.1
0x8e1a  ldarg.3
0x8e1b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool firstInstance)
0x8e20  ret
0x8e21  ldarg.0
0x8e22  ldarg.1
0x8e23  ldarg.3
0x8e24  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool firstInstance)
0x8e29  ldarg.0
0x8e2a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8e2f  ldloc.0
0x8e30  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint::get_DataElementName()
0x8e35  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8e3a  stloc.s  5
0x8e3c  ldloc.s  5
0x8e3e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8e43  brfalse.s loc_8E52
0x8e45  ldarg.0
0x8e46  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8e4b  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultChartDataPointTag()
0x8e50  stloc.s  5
0x8e52  ldarg.0
0x8e53  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8e58  ldloc.s  5
0x8e5a  ldarg.3
0x8e5b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartChartDataPoint(string name, bool firstInstance)
0x8e60  ldarg.0
0x8e61  ldloc.0
0x8e62  ldloc.1
0x8e63  ldloc.2
0x8e64  ldarg.2
0x8e65  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_DataValueSequenceRendering()
0x8e6a  ldarg.3
0x8e6b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTopLevelChartDataPoint(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint dataPoint, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool oldDataPointsGeneration, bool firstInstance)
0x8e70  ldarg.0
0x8e71  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8e76  ldarg.3
0x8e77  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x8e7c  ret
0x8e7d  ldarg.0
0x8e7e  ldarg.1
0x8e7f  ldarg.0
0x8e80  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x8e85  ldarg.3
0x8e86  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool attributesOnly, bool firstInstance)
0x8e8b  ldarg.0
0x8e8c  ldloc.0
0x8e8d  ldloc.1
0x8e8e  ldloc.2
0x8e8f  ldarg.2
0x8e90  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_DataValueSequenceRendering()
0x8e95  ldarg.0
0x8e96  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_DoAttributesPass
0x8e9b  ldarg.3
0x8e9c  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPoint(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint dataPoint, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool oldDataPointsGeneration, bool attributesOnly, bool firstInstance)
0x8ea1  stloc.s  6
0x8ea3  brfalse.s loc_8EAF
0x8ea5  ldarg.0
0x8ea6  ldarg.1
0x8ea7  ldc.i4.0
0x8ea8  ldarg.3
0x8ea9  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember chartMember, bool attributesOnly, bool firstInstance)
0x8eae  pop
0x8eaf  ldloc.s  6
0x8eb1  brfalse.s loc_8EC5
0x8eb3  ldarg.0
0x8eb4  ldloc.0
0x8eb5  ldloc.1
0x8eb6  ldloc.2
0x8eb7  ldarg.2
0x8eb8  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart::get_DataValueSequenceRendering()
0x8ebd  ldc.i4.0
0x8ebe  ldarg.3
0x8ebf  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPoint(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint dataPoint, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool oldDataPointsGeneration, bool attributesOnly, bool firstInstance)
0x8ec4  pop
0x8ec5  ret
```
