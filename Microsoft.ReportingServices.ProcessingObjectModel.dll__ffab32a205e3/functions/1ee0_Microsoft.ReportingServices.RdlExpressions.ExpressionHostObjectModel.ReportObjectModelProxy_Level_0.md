# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::Level_0

- ea: `0x1ee0`
- end: `0x1eed`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::Level_0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x320`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  ldarg.0
0x1ee1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1ee6  ldarg.1
0x1ee7  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::RecursiveLevel(string scope)
0x1eec  ret
```
