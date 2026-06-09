# Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::StartRowsArray

- ea: `0x5d40`
- end: `0x5d6b`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::StartRowsArray`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5c40`
- `0x5c50`

## callees

- `0x5d40`
- `0x60e0`
- `0x62b0`

## pseudocode

```c

```

## disassembly

```asm
0x5d40  ldarg.0
0x5d41  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::inRowsArray
0x5d46  brtrue.s loc_5D6A
0x5d48  ldarg.0
0x5d49  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5d4e  ldstr    aRows// "Rows"
0x5d53  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyName(string name)
0x5d58  ldarg.0
0x5d59  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5d5e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::StartArray()
0x5d63  ldarg.0
0x5d64  ldc.i4.1
0x5d65  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::inRowsArray
0x5d6a  ret
```
