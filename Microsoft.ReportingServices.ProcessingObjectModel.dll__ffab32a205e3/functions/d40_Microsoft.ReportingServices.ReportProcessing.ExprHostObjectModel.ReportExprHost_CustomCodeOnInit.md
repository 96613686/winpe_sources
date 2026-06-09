# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::CustomCodeOnInit

- ea: `0xd40`
- end: `0xd54`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::CustomCodeOnInit`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xa00`
- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldarg.0
0xd41  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomCodeProxyBase Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::m_codeProxyBase
0xd46  brfalse.s loc_D53
0xd48  ldarg.0
0xd49  ldfld    class Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomCodeProxyBase Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::m_codeProxyBase
0xd4e  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.CustomCodeProxyBase::CallOnInit()
0xd53  ret
```
