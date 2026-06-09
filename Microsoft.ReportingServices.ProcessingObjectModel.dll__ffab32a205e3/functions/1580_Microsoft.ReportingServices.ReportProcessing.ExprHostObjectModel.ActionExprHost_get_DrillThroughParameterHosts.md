# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::get_DrillThroughParameterHostsRemotable

- ea: `0x1580`
- end: `0x15a8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::get_DrillThroughParameterHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldarg.0
0x1581  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::m_drillThroughParameterHostsRemotable
0x1586  brtrue.s loc_15A1
0x1588  ldarg.0
0x1589  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::DrillThroughParameterHosts
0x158e  brfalse.s loc_15A1
0x1590  ldarg.0
0x1591  ldarg.0
0x1592  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::DrillThroughParameterHosts
0x1597  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost>::.ctor(var<u1>[])
0x159c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::m_drillThroughParameterHostsRemotable
0x15a1  ldarg.0
0x15a2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActionExprHost::m_drillThroughParameterHostsRemotable
0x15a7  ret
```
