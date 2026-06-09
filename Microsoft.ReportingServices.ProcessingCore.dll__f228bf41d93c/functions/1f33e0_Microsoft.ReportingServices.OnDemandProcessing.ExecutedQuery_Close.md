# Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::Close

- ea: `0x1f33e0`
- end: `0x1f346a`
- name: `Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::Close`
- size: `138`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f3020`
- `0x1f3520`
- `0x1f71d0`
- `0x1f7640`

## callees

- `0x114be0`
- `0x1f33e0`
- `0x1f6c40`

## string_xrefs

- `0x1f33f2`: `data reader`
- `0x1f342c`: `command`

## pseudocode

```c

```

## disassembly

```asm
0x1f33e0  ldarg.0
0x1f33e1  ldflda   class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_dataReader
0x1f33e6  ldnull
0x1f33e7  call     T0x2B000177
0x1f33ec  stloc.0
0x1f33ed  ldloc.0
0x1f33ee  brfalse.s loc_1F3413
0x1f33f0  ldloca.s 0
0x1f33f2  ldstr    aDataReader// "data reader"
0x1f33f7  ldarg.0
0x1f33f8  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_dataSet
0x1f33fd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f3402  ldarg.0
0x1f3403  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_executionMetrics
0x1f3408  ldc.i4.4
0x1f3409  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype MetricType>::.ctor(var<u1>)
0x1f340e  call     T0x2B000178
0x1f3413  ldarg.0
0x1f3414  ldnull
0x1f3415  stfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_commandWrappedForCancel
0x1f341a  ldarg.0
0x1f341b  ldflda   class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_command
0x1f3420  ldnull
0x1f3421  call     T0x2B000179
0x1f3426  stloc.1
0x1f3427  ldloc.1
0x1f3428  brfalse.s loc_1F3441
0x1f342a  ldloca.s 1
0x1f342c  ldstr    aCommand_0// "command"
0x1f3431  ldarg.0
0x1f3432  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_dataSet
0x1f3437  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x1f343c  call     T0x2B00017A
0x1f3441  ldarg.0
0x1f3442  ldflda   class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_connection
0x1f3447  ldnull
0x1f3448  call     T0x2B00017B
0x1f344d  stloc.2
0x1f344e  ldloc.2
0x1f344f  brfalse.s loc_1F3469
0x1f3451  ldloc.2
0x1f3452  ldarg.0
0x1f3453  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_dataSource
0x1f3458  ldarg.0
0x1f3459  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_odpContext
0x1f345e  ldarg.0
0x1f345f  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::m_executionMetrics
0x1f3464  call     void Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSource::CloseConnection(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection connection, class Microsoft.ReportingServices.ReportIntermediateFormat.DataSource dataSource, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext, class Microsoft.ReportingServices.OnDemandProcessing.DataProcessingMetrics executionMetrics)
0x1f3469  ret
```
