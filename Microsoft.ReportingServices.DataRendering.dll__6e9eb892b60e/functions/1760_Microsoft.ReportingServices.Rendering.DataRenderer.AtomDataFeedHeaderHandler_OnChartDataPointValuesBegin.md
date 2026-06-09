# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnChartDataPointValuesBegin

- ea: `0x1760`
- end: `0x188b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::OnChartDataPointValuesBegin`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1890`
- `0x51e0`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldarg.1
0x1761  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x1766  ldnull
0x1767  cgt.un
0x1769  stloc.0
0x176a  ldarg.0
0x176b  ldarg.1
0x176c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_X()
0x1771  ldarg.0
0x1772  ldstr    aX// "X"
0x1777  ldc.i4.0
0x1778  ldarg.3
0x1779  ldarg.s  4
0x177b  ldarg.s  5
0x177d  ldloc.0
0x177e  ldarg.s  6
0x1780  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1785  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x178a  ldarg.0
0x178b  ldarg.1
0x178c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Y()
0x1791  ldarg.0
0x1792  ldstr    aY// "Y"
0x1797  ldc.i4.1
0x1798  ldarg.3
0x1799  ldarg.s  4
0x179b  ldarg.s  5
0x179d  ldloc.0
0x179e  ldarg.s  6
0x17a0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x17a5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x17aa  ldarg.0
0x17ab  ldarg.1
0x17ac  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Size()
0x17b1  ldarg.0
0x17b2  ldstr    aSize// "Size"
0x17b7  ldc.i4.2
0x17b8  ldarg.3
0x17b9  ldarg.s  4
0x17bb  ldarg.s  5
0x17bd  ldloc.0
0x17be  ldarg.s  6
0x17c0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x17c5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x17ca  ldarg.0
0x17cb  ldarg.1
0x17cc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_High()
0x17d1  ldarg.0
0x17d2  ldstr    aHigh// "High"
0x17d7  ldc.i4.3
0x17d8  ldarg.3
0x17d9  ldarg.s  4
0x17db  ldarg.s  5
0x17dd  ldloc.0
0x17de  ldarg.s  6
0x17e0  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x17e5  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x17ea  ldarg.0
0x17eb  ldarg.1
0x17ec  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Low()
0x17f1  ldarg.0
0x17f2  ldstr    aLow// "Low"
0x17f7  ldc.i4.4
0x17f8  ldarg.3
0x17f9  ldarg.s  4
0x17fb  ldarg.s  5
0x17fd  ldloc.0
0x17fe  ldarg.s  6
0x1800  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1805  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x180a  ldarg.0
0x180b  ldarg.1
0x180c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x1811  ldarg.0
0x1812  ldstr    aStart// "Start"
0x1817  ldc.i4.5
0x1818  ldarg.3
0x1819  ldarg.s  4
0x181b  ldarg.s  5
0x181d  ldloc.0
0x181e  ldarg.s  6
0x1820  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1825  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x182a  ldarg.0
0x182b  ldarg.1
0x182c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_End()
0x1831  ldarg.0
0x1832  ldstr    aEnd// "End"
0x1837  ldc.i4.6
0x1838  ldarg.3
0x1839  ldarg.s  4
0x183b  ldarg.s  5
0x183d  ldloc.0
0x183e  ldarg.s  6
0x1840  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1845  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x184a  ldarg.0
0x184b  ldarg.1
0x184c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Mean()
0x1851  ldarg.0
0x1852  ldstr    aMean// "Mean"
0x1857  ldc.i4.7
0x1858  ldarg.3
0x1859  ldarg.s  4
0x185b  ldarg.s  5
0x185d  ldloc.0
0x185e  ldarg.s  6
0x1860  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1865  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x186a  ldarg.0
0x186b  ldarg.1
0x186c  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Median()
0x1871  ldarg.0
0x1872  ldstr    aMedian// "Median"
0x1877  ldc.i4.8
0x1878  ldarg.3
0x1879  ldarg.s  4
0x187b  ldarg.s  5
0x187d  ldloc.0
0x187e  ldarg.s  6
0x1880  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName(string colName, valuetype DataPointValueProperties dataPointValueProperty, bool oldDataPointsGeneration, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subType, bool hasStart, string parentScopeName)
0x1885  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty dataPointValue, string colName)
0x188a  ret
```
