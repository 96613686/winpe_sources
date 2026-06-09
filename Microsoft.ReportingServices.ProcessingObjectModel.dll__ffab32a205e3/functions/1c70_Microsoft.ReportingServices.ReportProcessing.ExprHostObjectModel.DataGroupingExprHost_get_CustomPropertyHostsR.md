# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::get_CustomPropertyHostsRemotable

- ea: `0x1c70`
- end: `0x1c98`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::get_CustomPropertyHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c70`

## pseudocode

```c

```

## disassembly

```asm
0x1c70  ldarg.0
0x1c71  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_customPropertyHostsRemotable
0x1c76  brtrue.s loc_1C91
0x1c78  ldarg.0
0x1c79  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::CustomPropertyHosts
0x1c7e  brfalse.s loc_1C91
0x1c80  ldarg.0
0x1c81  ldarg.0
0x1c82  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::CustomPropertyHosts
0x1c87  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost>::.ctor(var<u1>[])
0x1c8c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_customPropertyHostsRemotable
0x1c91  ldarg.0
0x1c92  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataGroupingExprHost::m_customPropertyHostsRemotable
0x1c97  ret
```
