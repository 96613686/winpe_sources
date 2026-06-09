# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::Level

- ea: `0x1ed0`
- end: `0x1edd`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::Level`
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
0x1ed0  ldarg.0
0x1ed1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1ed6  ldnull
0x1ed7  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::RecursiveLevel(string scope)
0x1edc  ret
```
