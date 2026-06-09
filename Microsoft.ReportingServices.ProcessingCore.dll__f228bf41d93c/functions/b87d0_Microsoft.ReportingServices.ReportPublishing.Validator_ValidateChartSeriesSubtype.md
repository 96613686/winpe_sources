# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartSeriesSubtype

- ea: `0xb87d0`
- end: `0xb8942`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartSeriesSubtype`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xa6830`

## callees

- `0xb87d0`
- `0xb9aa0`
- `0xb9b10`
- `0xbd050`
- `0xbd070`

## string_xrefs

- `0xb88eb`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xb890e`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xb87d0  ldarg.0
0xb87d1  ldstr    aPlain// "Plain"
0xb87d6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb87db  brtrue   loc_B88E2
0xb87e0  ldarg.0
0xb87e1  ldstr    aStacked// "Stacked"
0xb87e6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb87eb  brtrue   loc_B88E2
0xb87f0  ldarg.0
0xb87f1  ldstr    aPercentstacked// "PercentStacked"
0xb87f6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb87fb  brtrue   loc_B88E2
0xb8800  ldarg.0
0xb8801  ldstr    aSmooth// "Smooth"
0xb8806  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb880b  brtrue   loc_B88E2
0xb8810  ldarg.0
0xb8811  ldstr    aStepped// "Stepped"
0xb8816  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb881b  brtrue   loc_B88E2
0xb8820  ldarg.0
0xb8821  ldstr    aPie// "Pie"
0xb8826  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb882b  brtrue   loc_B88E2
0xb8830  ldarg.0
0xb8831  ldstr    aExplodedpie// "ExplodedPie"
0xb8836  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb883b  brtrue   loc_B88E2
0xb8840  ldarg.0
0xb8841  ldstr    aDoughnut// "Doughnut"
0xb8846  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb884b  brtrue   loc_B88E2
0xb8850  ldarg.0
0xb8851  ldstr    aExplodeddoughn// "ExplodedDoughnut"
0xb8856  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb885b  brtrue   loc_B88E2
0xb8860  ldarg.0
0xb8861  ldstr    aFunnel// "Funnel"
0xb8866  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb886b  brtrue.s loc_B88E2
0xb886d  ldarg.0
0xb886e  ldstr    aPyramid// "Pyramid"
0xb8873  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8878  brtrue.s loc_B88E2
0xb887a  ldarg.0
0xb887b  ldstr    aBubble// "Bubble"
0xb8880  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8885  brtrue.s loc_B88E2
0xb8887  ldarg.0
0xb8888  ldstr    aCandlestick_0// "Candlestick"
0xb888d  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8892  brtrue.s loc_B88E2
0xb8894  ldarg.0
0xb8895  ldstr    aStock// "Stock"
0xb889a  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb889f  brtrue.s loc_B88E2
0xb88a1  ldarg.0
0xb88a2  ldstr    aBar// "Bar"
0xb88a7  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb88ac  brtrue.s loc_B88E2
0xb88ae  ldarg.0
0xb88af  ldstr    aColumn// "Column"
0xb88b4  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb88b9  brtrue.s loc_B88E2
0xb88bb  ldarg.0
0xb88bc  ldstr    aBoxplot// "BoxPlot"
0xb88c1  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb88c6  brtrue.s loc_B88E2
0xb88c8  ldarg.0
0xb88c9  ldstr    aErrorbar// "ErrorBar"
0xb88ce  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb88d3  brtrue.s loc_B88E2
0xb88d5  ldarg.0
0xb88d6  ldstr    aRadar// "Radar"
0xb88db  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb88e0  brfalse.s loc_B88E4
0xb88e2  ldc.i4.1
0xb88e3  ret
0xb88e4  call     class Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::get_Instance()
0xb88e9  ldarg.s  4
0xb88eb  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xb88f0  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::Compare(string x, string y)
0xb88f5  ldc.i4.0
0xb88f6  blt.s    loc_B8907
0xb88f8  ldarg.0
0xb88f9  ldstr    aMap// "Map"
0xb88fe  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8903  brfalse.s loc_B8907
0xb8905  ldc.i4.1
0xb8906  ret
0xb8907  call     class Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::get_Instance()
0xb890c  ldarg.s  4
0xb890e  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xb8913  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::Compare(string x, string y)
0xb8918  ldc.i4.0
0xb8919  blt.s    loc_B8937
0xb891b  ldarg.0
0xb891c  ldstr    aTreemap// "TreeMap"
0xb8921  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8926  brtrue.s loc_B8935
0xb8928  ldarg.0
0xb8929  ldstr    aSunburst// "Sunburst"
0xb892e  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8933  brfalse.s loc_B8937
0xb8935  ldc.i4.1
0xb8936  ret
0xb8937  ldarg.0
0xb8938  ldarg.1
0xb8939  ldarg.2
0xb893a  ldarg.3
0xb893b  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb8940  ldc.i4.0
0xb8941  ret
```
