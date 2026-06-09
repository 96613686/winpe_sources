# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::get_DataGroupingHostsRemotable

- ea: `0x1ca0`
- end: `0x1cc8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::get_DataGroupingHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ca0`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_dataGroupingHostsRemotable
0x1ca6  brtrue.s loc_1CC1
0x1ca8  ldarg.0
0x1ca9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::DataGroupingHosts
0x1cae  brfalse.s loc_1CC1
0x1cb0  ldarg.0
0x1cb1  ldarg.0
0x1cb2  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::DataGroupingHosts
0x1cb7  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost>::.ctor(var<u1>[])
0x1cbc  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_dataGroupingHostsRemotable
0x1cc1  ldarg.0
0x1cc2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_dataGroupingHostsRemotable
0x1cc7  ret
```
