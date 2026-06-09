# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Parameters

- ea: `0x1e30`
- end: `0x1e3c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Parameters`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f20`

## callees

- `0x2a0`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldarg.0
0x1e31  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e36  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.Parameters Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_Parameters()
0x1e3b  ret
```
