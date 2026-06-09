# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::get_FieldHostsRemotable

- ea: `0x1120`
- end: `0x1148`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::get_FieldHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1120`

## pseudocode

```c

```

## disassembly

```asm
0x1120  ldarg.0
0x1121  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_fieldHostsRemotable
0x1126  brtrue.s loc_1141
0x1128  ldarg.0
0x1129  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::FieldHosts
0x112e  brfalse.s loc_1141
0x1130  ldarg.0
0x1131  ldarg.0
0x1132  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::FieldHosts
0x1137  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost>::.ctor(var<u1>[])
0x113c  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_fieldHostsRemotable
0x1141  ldarg.0
0x1142  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CalcFieldExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.DataSetExprHost::m_fieldHostsRemotable
0x1147  ret
```
