# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Variables

- ea: `0x1eb0`
- end: `0x1ebc`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_Variables`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f50`

## callees

- `0x10`

## pseudocode

```c

```

## disassembly

```asm
0x1eb0  ldarg.0
0x1eb1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1eb6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.Variables Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel::get_Variables()
0x1ebb  ret
```
