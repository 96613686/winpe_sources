# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::get_ActionItemHostsRemotable

- ea: `0x1510`
- end: `0x1538`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::get_ActionItemHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1510`

## pseudocode

```c

```

## disassembly

```asm
0x1510  ldarg.0
0x1511  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::m_actionItemHostsRemotable
0x1516  brtrue.s loc_1531
0x1518  ldarg.0
0x1519  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::ActionItemHosts
0x151e  brfalse.s loc_1531
0x1520  ldarg.0
0x1521  ldarg.0
0x1522  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::ActionItemHosts
0x1527  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost>::.ctor(var<u1>[])
0x152c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::m_actionItemHostsRemotable
0x1531  ldarg.0
0x1532  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionInfoExprHost::m_actionItemHostsRemotable
0x1537  ret
```
