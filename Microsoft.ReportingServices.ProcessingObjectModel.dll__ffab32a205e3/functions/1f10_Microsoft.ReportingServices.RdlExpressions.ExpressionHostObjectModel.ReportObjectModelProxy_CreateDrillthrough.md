# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::CreateDrillthroughContext

- ea: `0x1f10`
- end: `0x1f1c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::CreateDrillthroughContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x330`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1f16  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::CreateDrillthroughContext()
0x1f1b  ret
```
