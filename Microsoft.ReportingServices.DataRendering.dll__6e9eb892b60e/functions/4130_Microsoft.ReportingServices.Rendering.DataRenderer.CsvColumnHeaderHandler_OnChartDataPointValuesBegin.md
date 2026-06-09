# Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnChartDataPointValuesBegin

- ea: `0x4130`
- end: `0x425b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::OnChartDataPointValuesBegin`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x4260`
- `0x51e0`

## pseudocode

```c

```

## disassembly

```asm
0x4130  ldarg.1
0x4131  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x4136  ldnull
0x4137  cgt.un
0x4139  stloc.0
0x413a  ldarg.0
0x413b  ldarg.1
0x413c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_X()
0x4141  ldarg.0
0x4142  ldstr    aX// "X"
0x4147  ldc.i4.0
0x4148  ldarg.3
0x4149  ldarg.s  4
0x414b  ldarg.s  5
0x414d  ldloc.0
0x414e  ldarg.s  6
0x4150  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4155  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x415a  ldarg.0
0x415b  ldarg.1
0x415c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Y()
0x4161  ldarg.0
0x4162  ldstr    aY// "Y"
0x4167  ldc.i4.1
0x4168  ldarg.3
0x4169  ldarg.s  4
0x416b  ldarg.s  5
0x416d  ldloc.0
0x416e  ldarg.s  6
0x4170  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4175  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x417a  ldarg.0
0x417b  ldarg.1
0x417c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Size()
0x4181  ldarg.0
0x4182  ldstr    aSize// "Size"
0x4187  ldc.i4.2
0x4188  ldarg.3
0x4189  ldarg.s  4
0x418b  ldarg.s  5
0x418d  ldloc.0
0x418e  ldarg.s  6
0x4190  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4195  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x419a  ldarg.0
0x419b  ldarg.1
0x419c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_High()
0x41a1  ldarg.0
0x41a2  ldstr    aHigh// "High"
0x41a7  ldc.i4.3
0x41a8  ldarg.3
0x41a9  ldarg.s  4
0x41ab  ldarg.s  5
0x41ad  ldloc.0
0x41ae  ldarg.s  6
0x41b0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x41b5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x41ba  ldarg.0
0x41bb  ldarg.1
0x41bc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Low()
0x41c1  ldarg.0
0x41c2  ldstr    aLow// "Low"
0x41c7  ldc.i4.4
0x41c8  ldarg.3
0x41c9  ldarg.s  4
0x41cb  ldarg.s  5
0x41cd  ldloc.0
0x41ce  ldarg.s  6
0x41d0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x41d5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x41da  ldarg.0
0x41db  ldarg.1
0x41dc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x41e1  ldarg.0
0x41e2  ldstr    aStart// "Start"
0x41e7  ldc.i4.5
0x41e8  ldarg.3
0x41e9  ldarg.s  4
0x41eb  ldarg.s  5
0x41ed  ldloc.0
0x41ee  ldarg.s  6
0x41f0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x41f5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x41fa  ldarg.0
0x41fb  ldarg.1
0x41fc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_End()
0x4201  ldarg.0
0x4202  ldstr    aEnd// "End"
0x4207  ldc.i4.6
0x4208  ldarg.3
0x4209  ldarg.s  4
0x420b  ldarg.s  5
0x420d  ldloc.0
0x420e  ldarg.s  6
0x4210  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4215  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x421a  ldarg.0
0x421b  ldarg.1
0x421c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Mean()
0x4221  ldarg.0
0x4222  ldstr    aMean// "Mean"
0x4227  ldc.i4.7
0x4228  ldarg.3
0x4229  ldarg.s  4
0x422b  ldarg.s  5
0x422d  ldloc.0
0x422e  ldarg.s  6
0x4230  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4235  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x423a  ldarg.0
0x423b  ldarg.1
0x423c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Median()
0x4241  ldarg.0
0x4242  ldstr    aMedian// "Median"
0x4247  ldc.i4.8
0x4248  ldarg.3
0x4249  ldarg.s  4
0x424b  ldarg.s  5
0x424d  ldloc.0
0x424e  ldarg.s  6
0x4250  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x4255  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.CsvColumnHeaderHandler::WriteDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x425a  ret
```
