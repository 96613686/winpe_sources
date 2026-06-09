# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::MaxValue

- ea: `0x1f00`
- end: `0x1f0d`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::MaxValue`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x40`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.0
0x1f01  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1f06  ldarg.1
0x1f07  callvirt instance object Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel::MaxValue(object[] arguments)
0x1f0c  ret
```
