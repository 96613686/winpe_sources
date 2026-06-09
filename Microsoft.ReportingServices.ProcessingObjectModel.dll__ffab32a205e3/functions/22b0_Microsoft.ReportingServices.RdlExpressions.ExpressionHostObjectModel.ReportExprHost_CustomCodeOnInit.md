# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::CustomCodeOnInit

- ea: `0x22b0`
- end: `0x22c4`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::CustomCodeOnInit`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1da0`
- `0x22b0`

## pseudocode

```c

```

## disassembly

```asm
0x22b0  ldarg.0
0x22b1  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.CustomCodeProxyBase Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::m_codeProxyBase
0x22b6  brfalse.s loc_22C3
0x22b8  ldarg.0
0x22b9  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.CustomCodeProxyBase Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::m_codeProxyBase
0x22be  callvirt instance void Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.CustomCodeProxyBase::CallOnInit()
0x22c3  ret
```
