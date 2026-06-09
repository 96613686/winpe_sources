# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::get_CustomPropertyHostsRemotable

- ea: `0x18b0`
- end: `0x18d8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::get_CustomPropertyHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18b0`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldarg.0
0x18b1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_customPropertyHostsRemotable
0x18b6  brtrue.s loc_18D1
0x18b8  ldarg.0
0x18b9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::CustomPropertyHosts
0x18be  brfalse.s loc_18D1
0x18c0  ldarg.0
0x18c1  ldarg.0
0x18c2  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::CustomPropertyHosts
0x18c7  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost>::.ctor(var<u1>[])
0x18cc  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_customPropertyHostsRemotable
0x18d1  ldarg.0
0x18d2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.GroupingExprHost::m_customPropertyHostsRemotable
0x18d7  ret
```
