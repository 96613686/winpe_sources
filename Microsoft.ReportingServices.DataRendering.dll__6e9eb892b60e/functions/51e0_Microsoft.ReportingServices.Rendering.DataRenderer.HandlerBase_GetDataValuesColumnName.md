# Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName

- ea: `0x51e0`
- end: `0x5221`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::GetDataValuesColumnName`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1760`
- `0x4130`

## callees

- `0x51e0`
- `0x5370`

## pseudocode

```c

```

## disassembly

```asm
0x51e0  ldarg.3
0x51e1  brfalse.s loc_5213
0x51e3  ldarg.0
0x51e4  ldarg.2
0x51e5  ldarg.s  4
0x51e7  ldarg.s  5
0x51e9  ldarg.s  6
0x51eb  call     instance int32 Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::MapDataValueName(valuetype DataPointValueProperties dataPointValueProperty, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesType type, valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartSeriesSubtype subtype, bool hasStart)
0x51f0  stloc.0
0x51f1  ldarg.s  7
0x51f3  ldstr    asc_EEAC// "_"
0x51f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x51fd  ldstr    aDatavalue0// "DataValue{0}"
0x5202  ldloc.0
0x5203  box      [mscorlib]System.Int32
0x5208  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x520d  call     string [mscorlib]System.String::Concat(string, string, string)
0x5212  ret
0x5213  ldarg.s  7
0x5215  ldstr    asc_EEAC// "_"
0x521a  ldarg.1
0x521b  call     string [mscorlib]System.String::Concat(string, string, string)
0x5220  ret
```
