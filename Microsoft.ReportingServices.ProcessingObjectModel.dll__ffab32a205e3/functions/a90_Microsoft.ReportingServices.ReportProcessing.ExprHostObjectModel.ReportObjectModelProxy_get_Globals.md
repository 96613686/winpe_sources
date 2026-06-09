# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_Globals

- ea: `0xa90`
- end: `0xa9c`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_Globals`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb40`

## callees

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldarg.0
0xa91  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0xa96  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.Globals Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_Globals()
0xa9b  ret
```
