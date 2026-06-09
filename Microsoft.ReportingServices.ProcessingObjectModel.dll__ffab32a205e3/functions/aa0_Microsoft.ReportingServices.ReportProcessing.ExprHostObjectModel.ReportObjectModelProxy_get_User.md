# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_User

- ea: `0xaa0`
- end: `0xaac`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::get_User`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb50`

## callees

- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::m_reportObjectModel
0xaa6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.User Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel::get_User()
0xaab  ret
```
