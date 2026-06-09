# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Globals

- ea: `0x1e40`
- end: `0x1e4c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Globals`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f30`

## callees

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x1e40  ldarg.0
0x1e41  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e46  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.Globals Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_Globals()
0x1e4b  ret
```
