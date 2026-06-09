# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::get_DataValueHostsRemotable

- ea: `0x1c20`
- end: `0x1c48`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::get_DataValueHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c20`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  ldarg.0
0x1c21  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::m_dataValueHostsRemotable
0x1c26  brtrue.s loc_1C41
0x1c28  ldarg.0
0x1c29  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::DataValueHosts
0x1c2e  brfalse.s loc_1C41
0x1c30  ldarg.0
0x1c31  ldarg.0
0x1c32  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::DataValueHosts
0x1c37  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost>::.ctor(var<u1>[])
0x1c3c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::m_dataValueHostsRemotable
0x1c41  ldarg.0
0x1c42  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataCellExprHost::m_dataValueHostsRemotable
0x1c47  ret
```
