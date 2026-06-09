# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::get_FilterHostsRemotable

- ea: `0x1160`
- end: `0x1188`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::get_FilterHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1160`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.0
0x1161  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_filterHostsRemotable
0x1166  brtrue.s loc_1181
0x1168  ldarg.0
0x1169  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::FilterHosts
0x116e  brfalse.s loc_1181
0x1170  ldarg.0
0x1171  ldarg.0
0x1172  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::FilterHosts
0x1177  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost>::.ctor(var<u1>[])
0x117c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_filterHostsRemotable
0x1181  ldarg.0
0x1182  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_filterHostsRemotable
0x1187  ret
```
