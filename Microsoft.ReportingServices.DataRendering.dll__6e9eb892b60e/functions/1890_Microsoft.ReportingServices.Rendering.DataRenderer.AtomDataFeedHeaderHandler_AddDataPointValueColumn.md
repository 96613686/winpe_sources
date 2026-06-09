# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn

- ea: `0x1890`
- end: `0x18a0`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHeaderHandler::AddDataPointValueColumn`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1760`

## callees

- `0x1890`
- `0x35e0`

## pseudocode

```c

```

## disassembly

```asm
0x1890  ldarg.1
0x1891  brfalse.s loc_189F
0x1893  ldarg.0
0x1894  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1899  ldarg.2
0x189a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName)
0x189f  ret
```
