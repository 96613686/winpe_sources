# Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::OnRegionEnd

- ea: `0x5c80`
- end: `0x5ca1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::OnRegionEnd`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x5c80`
- `0x5cc0`
- `0x5d70`
- `0x5d90`
- `0x5fe0`

## pseudocode

```c

```

## disassembly

```asm
0x5c80  ldarg.0
0x5c81  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::tablixPresent
0x5c86  brtrue.s loc_5C8E
0x5c88  ldarg.0
0x5c89  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::EndRowArray()
0x5c8e  ldarg.0
0x5c8f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::EndRowsArray()
0x5c94  ldarg.0
0x5c95  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::WriteColumnsArray()
0x5c9a  ldarg.0
0x5c9b  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::WriteDataSetName()
0x5ca0  ret
```
