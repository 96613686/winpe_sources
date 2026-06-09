# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::MinValue

- ea: `0x1ef0`
- end: `0x1efd`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::MinValue`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x30`

## pseudocode

```c

```

## disassembly

```asm
0x1ef0  ldarg.0
0x1ef1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1ef6  ldarg.1
0x1ef7  callvirt instance object Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel::MinValue(object[] arguments)
0x1efc  ret
```
