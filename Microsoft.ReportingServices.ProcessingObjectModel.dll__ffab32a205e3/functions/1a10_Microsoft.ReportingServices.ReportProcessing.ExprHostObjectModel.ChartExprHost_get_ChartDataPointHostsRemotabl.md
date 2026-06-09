# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::get_ChartDataPointHostsRemotable

- ea: `0x1a10`
- end: `0x1a38`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::get_ChartDataPointHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a10`

## pseudocode

```c

```

## disassembly

```asm
0x1a10  ldarg.0
0x1a11  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::m_chartDataPointHostsRemotable
0x1a16  brtrue.s loc_1A31
0x1a18  ldarg.0
0x1a19  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::ChartDataPointHosts
0x1a1e  brfalse.s loc_1A31
0x1a20  ldarg.0
0x1a21  ldarg.0
0x1a22  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::ChartDataPointHosts
0x1a27  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost>::.ctor(var<u1>[])
0x1a2c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::m_chartDataPointHostsRemotable
0x1a31  ldarg.0
0x1a32  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartExprHost::m_chartDataPointHostsRemotable
0x1a37  ret
```
