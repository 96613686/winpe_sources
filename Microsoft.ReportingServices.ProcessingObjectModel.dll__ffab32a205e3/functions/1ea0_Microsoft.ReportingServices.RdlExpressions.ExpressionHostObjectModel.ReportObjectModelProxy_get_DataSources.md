# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_DataSources

- ea: `0x1ea0`
- end: `0x1eac`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_DataSources`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.0
0x1ea1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1ea6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.DataSources Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_DataSources()
0x1eab  ret
```
