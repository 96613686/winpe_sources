# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Lookups

- ea: `0x1e80`
- end: `0x1e8c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Lookups`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20`

## pseudocode

```c

```

## disassembly

```asm
0x1e80  ldarg.0
0x1e81  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e86  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.Lookups Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel::get_Lookups()
0x1e8b  ret
```
