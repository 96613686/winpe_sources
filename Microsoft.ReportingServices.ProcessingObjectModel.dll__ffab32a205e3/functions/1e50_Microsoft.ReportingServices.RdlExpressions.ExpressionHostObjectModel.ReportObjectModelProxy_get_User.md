# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_User

- ea: `0x1e50`
- end: `0x1e5c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::get_User`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f40`

## callees

- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0x1e50  ldarg.0
0x1e51  ldfld    class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0x1e56  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.User Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_User()
0x1e5b  ret
```
