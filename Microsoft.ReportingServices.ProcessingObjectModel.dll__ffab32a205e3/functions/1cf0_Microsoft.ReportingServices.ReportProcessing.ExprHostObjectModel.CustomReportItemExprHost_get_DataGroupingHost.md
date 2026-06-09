# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::get_DataGroupingHostsRemotable

- ea: `0x1cf0`
- end: `0x1d18`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::get_DataGroupingHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cf0`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldarg.0
0x1cf1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataGroupingHostsRemotable
0x1cf6  brtrue.s loc_1D11
0x1cf8  ldarg.0
0x1cf9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::DataGroupingHosts
0x1cfe  brfalse.s loc_1D11
0x1d00  ldarg.0
0x1d01  ldarg.0
0x1d02  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::DataGroupingHosts
0x1d07  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost>::.ctor(var<u1>[])
0x1d0c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataGroupingHostsRemotable
0x1d11  ldarg.0
0x1d12  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataGroupingHostsRemotable
0x1d17  ret
```
