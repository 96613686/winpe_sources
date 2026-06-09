# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::get_CustomPropertyHostsRemotable

- ea: `0x1b40`
- end: `0x1b68`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::get_CustomPropertyHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b40`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  ldarg.0
0x1b41  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::m_customPropertyHostsRemotable
0x1b46  brtrue.s loc_1B61
0x1b48  ldarg.0
0x1b49  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::CustomPropertyHosts
0x1b4e  brfalse.s loc_1B61
0x1b50  ldarg.0
0x1b51  ldarg.0
0x1b52  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::CustomPropertyHosts
0x1b57  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost>::.ctor(var<u1>[])
0x1b5c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::m_customPropertyHostsRemotable
0x1b61  ldarg.0
0x1b62  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.AxisExprHost::m_customPropertyHostsRemotable
0x1b67  ret
```
