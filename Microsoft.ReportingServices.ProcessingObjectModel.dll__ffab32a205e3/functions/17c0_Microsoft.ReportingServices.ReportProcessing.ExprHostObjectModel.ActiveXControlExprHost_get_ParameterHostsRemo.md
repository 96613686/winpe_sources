# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::get_ParameterHostsRemotable

- ea: `0x17c0`
- end: `0x17e8`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::get_ParameterHostsRemotable`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x17c0`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldarg.0
0x17c1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::m_parameterHostsRemotable
0x17c6  brtrue.s loc_17E1
0x17c8  ldarg.0
0x17c9  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::ParameterHosts
0x17ce  brfalse.s loc_17E1
0x17d0  ldarg.0
0x17d1  ldarg.0
0x17d2  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost[] Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::ParameterHosts
0x17d7  newobj   instance void class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.RemoteArrayWrapper`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost>::.ctor(var<u1>[])
0x17dc  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::m_parameterHostsRemotable
0x17e1  ldarg.0
0x17e2  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ParamExprHost> Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ActiveXControlExprHost::m_parameterHostsRemotable
0x17e7  ret
```
