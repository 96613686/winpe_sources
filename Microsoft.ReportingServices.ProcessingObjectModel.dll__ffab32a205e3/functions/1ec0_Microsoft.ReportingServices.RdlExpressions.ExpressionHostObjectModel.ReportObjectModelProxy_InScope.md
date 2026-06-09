# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::InScope

- ea: `0x1ec0`
- end: `0x1ecd`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::InScope`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldarg.0
0x1ec1  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1ec6  ldarg.1
0x1ec7  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::InScope(string scope)
0x1ecc  ret
```
