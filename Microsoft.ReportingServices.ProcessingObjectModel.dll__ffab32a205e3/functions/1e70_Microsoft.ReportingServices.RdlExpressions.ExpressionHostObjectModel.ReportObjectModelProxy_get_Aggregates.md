# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Aggregates

- ea: `0x1e70`
- end: `0x1e7c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Aggregates`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x1e70  ldarg.0
0x1e71  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e76  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.Aggregates Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_Aggregates()
0x1e7b  ret
```
