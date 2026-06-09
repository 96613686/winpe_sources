# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPoint

- ea: `0x8f00`
- end: `0x9207`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPoint`
- size: `775`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8d30`
- `0x8ed0`

## callees

- `0x8f00`
- `0x9210`
- `0x9240`
- `0xa180`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x8f05  ldarg.1
0x8f06  ldnull
0x8f07  cgt.un
0x8f09  ldstr    aWalkchartdatap// "WalkChartDataPoint: Null data point"
0x8f0e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8f13  ldarg.0
0x8f14  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x8f19  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x8f1e  ldc.i4.1
0x8f1f  ceq
0x8f21  stloc.0
0x8f22  ldloc.0
0x8f23  ldarg.s  5
0x8f25  bne.un.s loc_8F2A
0x8f27  ldarg.s  5
0x8f29  ret
0x8f2a  ldarg.1
0x8f2b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint::get_DataPointValues()
0x8f30  stloc.1
0x8f31  ldloc.1
0x8f32  brfalse  loc_9205
0x8f37  ldarg.1
0x8f38  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPoint::get_DataPointValues()
0x8f3d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Instance()
0x8f42  stloc.2
0x8f43  ldc.i4.0
0x8f44  stloc.3
0x8f45  ldloc.1
0x8f46  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_X()
0x8f4b  brfalse.s loc_8F93
0x8f4d  ldarg.s  4
0x8f4f  brfalse.s loc_8F7F
0x8f51  ldarg.0
0x8f52  ldstr    aX// "X"
0x8f57  ldarg.2
0x8f58  ldarg.3
0x8f59  ldloc.3
0x8f5a  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x8f5f  stloc.s  4
0x8f61  ldarg.0
0x8f62  ldarg.0
0x8f63  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8f68  ldloc.s  4
0x8f6a  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x8f6f  ldloc.2
0x8f70  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x8f75  ldloc.0
0x8f76  ldarg.s  6
0x8f78  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x8f7d  br.s     loc_8F93
0x8f7f  ldarg.0
0x8f80  ldstr    aX// "X"
0x8f85  ldloc.2
0x8f86  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x8f8b  ldloc.0
0x8f8c  ldarg.s  6
0x8f8e  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x8f93  ldloc.1
0x8f94  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Y()
0x8f99  brfalse.s loc_8FE1
0x8f9b  ldarg.s  4
0x8f9d  brfalse.s loc_8FCD
0x8f9f  ldarg.0
0x8fa0  ldstr    aY// "Y"
0x8fa5  ldarg.2
0x8fa6  ldarg.3
0x8fa7  ldloc.3
0x8fa8  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x8fad  stloc.s  5
0x8faf  ldarg.0
0x8fb0  ldarg.0
0x8fb1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8fb6  ldloc.s  5
0x8fb8  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x8fbd  ldloc.2
0x8fbe  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x8fc3  ldloc.0
0x8fc4  ldarg.s  6
0x8fc6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x8fcb  br.s     loc_8FE1
0x8fcd  ldarg.0
0x8fce  ldstr    aY// "Y"
0x8fd3  ldloc.2
0x8fd4  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x8fd9  ldloc.0
0x8fda  ldarg.s  6
0x8fdc  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x8fe1  ldloc.1
0x8fe2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Size()
0x8fe7  brfalse.s loc_902F
0x8fe9  ldarg.s  4
0x8feb  brfalse.s loc_901B
0x8fed  ldarg.0
0x8fee  ldstr    aSize// "Size"
0x8ff3  ldarg.2
0x8ff4  ldarg.3
0x8ff5  ldloc.3
0x8ff6  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x8ffb  stloc.s  6
0x8ffd  ldarg.0
0x8ffe  ldarg.0
0x8fff  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9004  ldloc.s  6
0x9006  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x900b  ldloc.2
0x900c  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x9011  ldloc.0
0x9012  ldarg.s  6
0x9014  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x9019  br.s     loc_902F
0x901b  ldarg.0
0x901c  ldstr    aSize// "Size"
0x9021  ldloc.2
0x9022  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x9027  ldloc.0
0x9028  ldarg.s  6
0x902a  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x902f  ldloc.1
0x9030  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_High()
0x9035  brfalse.s loc_907D
0x9037  ldarg.s  4
0x9039  brfalse.s loc_9069
0x903b  ldarg.0
0x903c  ldstr    aHigh// "High"
0x9041  ldarg.2
0x9042  ldarg.3
0x9043  ldloc.3
0x9044  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x9049  stloc.s  7
0x904b  ldarg.0
0x904c  ldarg.0
0x904d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9052  ldloc.s  7
0x9054  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x9059  ldloc.2
0x905a  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x905f  ldloc.0
0x9060  ldarg.s  6
0x9062  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x9067  br.s     loc_907D
0x9069  ldarg.0
0x906a  ldstr    aHigh// "High"
0x906f  ldloc.2
0x9070  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x9075  ldloc.0
0x9076  ldarg.s  6
0x9078  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x907d  ldloc.1
0x907e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Low()
0x9083  brfalse.s loc_90CB
0x9085  ldarg.s  4
0x9087  brfalse.s loc_90B7
0x9089  ldarg.0
0x908a  ldstr    aLow// "Low"
0x908f  ldarg.2
0x9090  ldarg.3
0x9091  ldloc.3
0x9092  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x9097  stloc.s  8
0x9099  ldarg.0
0x909a  ldarg.0
0x909b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x90a0  ldloc.s  8
0x90a2  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x90a7  ldloc.2
0x90a8  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x90ad  ldloc.0
0x90ae  ldarg.s  6
0x90b0  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x90b5  br.s     loc_90CB
0x90b7  ldarg.0
0x90b8  ldstr    aLow// "Low"
0x90bd  ldloc.2
0x90be  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x90c3  ldloc.0
0x90c4  ldarg.s  6
0x90c6  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x90cb  ldloc.1
0x90cc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x90d1  brfalse.s loc_911B
0x90d3  ldc.i4.1
0x90d4  stloc.3
0x90d5  ldarg.s  4
0x90d7  brfalse.s loc_9107
0x90d9  ldarg.0
0x90da  ldstr    aStart// "Start"
0x90df  ldarg.2
0x90e0  ldarg.3
0x90e1  ldloc.3
0x90e2  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x90e7  stloc.s  9
0x90e9  ldarg.0
0x90ea  ldarg.0
0x90eb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x90f0  ldloc.s  9
0x90f2  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x90f7  ldloc.2
0x90f8  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x90fd  ldloc.0
0x90fe  ldarg.s  6
0x9100  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x9105  br.s     loc_911B
0x9107  ldarg.0
0x9108  ldstr    aStart// "Start"
0x910d  ldloc.2
0x910e  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x9113  ldloc.0
0x9114  ldarg.s  6
0x9116  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x911b  ldloc.1
0x911c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_End()
0x9121  brfalse.s loc_9169
0x9123  ldarg.s  4
0x9125  brfalse.s loc_9155
0x9127  ldarg.0
0x9128  ldstr    aEnd// "End"
0x912d  ldarg.2
0x912e  ldarg.3
0x912f  ldloc.3
0x9130  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x9135  stloc.s  0xA
0x9137  ldarg.0
0x9138  ldarg.0
0x9139  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x913e  ldloc.s  0xA
0x9140  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x9145  ldloc.2
0x9146  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x914b  ldloc.0
0x914c  ldarg.s  6
0x914e  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x9153  br.s     loc_9169
0x9155  ldarg.0
0x9156  ldstr    aEnd// "End"
0x915b  ldloc.2
0x915c  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x9161  ldloc.0
0x9162  ldarg.s  6
0x9164  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x9169  ldloc.1
0x916a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Mean()
0x916f  brfalse.s loc_91B7
0x9171  ldarg.s  4
0x9173  brfalse.s loc_91A3
0x9175  ldarg.0
0x9176  ldstr    aMean// "Mean"
0x917b  ldarg.2
0x917c  ldarg.3
0x917d  ldloc.3
0x917e  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x9183  stloc.s  0xB
0x9185  ldarg.0
0x9186  ldarg.0
0x9187  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x918c  ldloc.s  0xB
0x918e  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x9193  ldloc.2
0x9194  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x9199  ldloc.0
0x919a  ldarg.s  6
0x919c  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x91a1  br.s     loc_91B7
0x91a3  ldarg.0
0x91a4  ldstr    aMean// "Mean"
0x91a9  ldloc.2
0x91aa  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x91af  ldloc.0
0x91b0  ldarg.s  6
0x91b2  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x91b7  ldloc.1
0x91b8  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Median()
0x91bd  brfalse.s loc_9205
0x91bf  ldarg.s  4
0x91c1  brfalse.s loc_91F1
0x91c3  ldarg.0
0x91c4  ldstr    aMedian// "Median"
0x91c9  ldarg.2
0x91ca  ldarg.3
0x91cb  ldloc.3
0x91cc  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::DataValueMappingTable(string name, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x91d1  stloc.s  0xC
0x91d3  ldarg.0
0x91d4  ldarg.0
0x91d5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x91da  ldloc.s  0xC
0x91dc  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartDataValueTag(int32 aIndex)
0x91e1  ldloc.2
0x91e2  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x91e7  ldloc.0
0x91e8  ldarg.s  6
0x91ea  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
0x91ef  br.s     loc_9205
0x91f1  ldarg.0
0x91f2  ldstr    aMedian// "Median"
0x91f7  ldloc.2
0x91f8  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x91fd  ldloc.0
0x91fe  ldarg.s  6
0x9200  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue(string name, object value, bool renderAsElement, bool firstInstance)
  ... truncated ...
```
