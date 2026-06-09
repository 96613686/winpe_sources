# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::get_FilterHostsRemotable

- ea: `0x1880`
- end: `0x18a8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::get_FilterHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1880`

## pseudocode

```c

```

## disassembly

```asm
0x1880  ldarg.0
0x1881  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_filterHostsRemotable
0x1886  brtrue.s loc_18A1
0x1888  ldarg.0
0x1889  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::FilterHosts
0x188e  brfalse.s loc_18A1
0x1890  ldarg.0
0x1891  ldarg.0
0x1892  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::FilterHosts
0x1897  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost>::.ctor(var<u1>[])
0x189c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_filterHostsRemotable
0x18a1  ldarg.0
0x18a2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.FilterExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_filterHostsRemotable
0x18a7  ret
```
