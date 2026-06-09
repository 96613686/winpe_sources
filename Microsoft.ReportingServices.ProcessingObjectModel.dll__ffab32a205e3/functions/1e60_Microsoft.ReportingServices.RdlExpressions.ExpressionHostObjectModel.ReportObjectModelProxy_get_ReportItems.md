# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_ReportItems

- ea: `0x1e60`
- end: `0x1e6c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_ReportItems`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2d0`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.0
0x1e61  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e66  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ReportItems Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_ReportItems()
0x1e6b  ret
```
