# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextBoxExprHost::get_Value

- ea: `0x2b00`
- end: `0x2b0c`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextBoxExprHost::get_Value`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x6b0`

## pseudocode

```c

```

## disassembly

```asm
0x2b00  ldarg.0
0x2b01  ldfld    class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ReportItem Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.TextBoxExprHost::m_textBox
0x2b06  callvirt instance object Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ReportItem::get_Value()
0x2b0b  ret
```
