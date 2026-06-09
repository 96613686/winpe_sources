# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_Parameters

- ea: `0xa80`
- end: `0xa8c`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_Parameters`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb30`

## callees

- `0x2a0`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldarg.0
0xa81  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0xa86  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.Parameters Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_Parameters()
0xa8b  ret
```
