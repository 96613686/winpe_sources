# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::get_DataCellHostsRemotable

- ea: `0x1d20`
- end: `0x1d48`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::get_DataCellHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1d20`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.0
0x1d21  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataCellHostsRemotable
0x1d26  brtrue.s loc_1D41
0x1d28  ldarg.0
0x1d29  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::DataCellHosts
0x1d2e  brfalse.s loc_1D41
0x1d30  ldarg.0
0x1d31  ldarg.0
0x1d32  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::DataCellHosts
0x1d37  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost>::.ctor(var<u1>[])
0x1d3c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataCellHostsRemotable
0x1d41  ldarg.0
0x1d42  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomReportItemExprHost::m_dataCellHostsRemotable
0x1d47  ret
```
