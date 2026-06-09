# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::get_CustomPropertyHostsRemotable

- ea: `0x1ac0`
- end: `0x1ae8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::get_CustomPropertyHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ac0`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.0
0x1ac1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::m_customPropertyHostsRemotable
0x1ac6  brtrue.s loc_1AE1
0x1ac8  ldarg.0
0x1ac9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::CustomPropertyHosts
0x1ace  brfalse.s loc_1AE1
0x1ad0  ldarg.0
0x1ad1  ldarg.0
0x1ad2  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::CustomPropertyHosts
0x1ad7  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost>::.ctor(var<u1>[])
0x1adc  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::m_customPropertyHostsRemotable
0x1ae1  ldarg.0
0x1ae2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataValueExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ChartDataPointExprHost::m_customPropertyHostsRemotable
0x1ae7  ret
```
