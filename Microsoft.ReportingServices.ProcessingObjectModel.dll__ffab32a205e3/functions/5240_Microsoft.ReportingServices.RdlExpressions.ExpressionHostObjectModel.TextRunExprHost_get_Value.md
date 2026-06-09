# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextRunExprHost::get_Value

- ea: `0x5240`
- end: `0x524c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextRunExprHost::get_Value`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x260`

## pseudocode

```c

```

## disassembly

```asm
0x5240  ldarg.0
0x5241  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.TextRun Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextRunExprHost::m_textRun
0x5246  callvirt instance object Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.TextRun::get_Value()
0x524b  ret
```
