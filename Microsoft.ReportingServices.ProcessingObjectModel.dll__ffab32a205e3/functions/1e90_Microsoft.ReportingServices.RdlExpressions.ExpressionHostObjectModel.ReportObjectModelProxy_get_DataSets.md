# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_DataSets

- ea: `0x1e90`
- end: `0x1e9c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_DataSets`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e96  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.DataSets Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_DataSets()
0x1e9b  ret
```
