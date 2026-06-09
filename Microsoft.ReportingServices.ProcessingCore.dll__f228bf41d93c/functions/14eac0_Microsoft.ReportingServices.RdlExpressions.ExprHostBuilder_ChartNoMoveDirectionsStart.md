# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartNoMoveDirectionsStart

- ea: `0x14eac0`
- end: `0x14ead1`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartNoMoveDirectionsStart`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe2f0`

## callees

- `0x152580`

## string_xrefs

- `0x14eac1`: `ChartNoMoveDirections`
- `0x14eac6`: `ChartNoMoveDirectionsExprHost`

## pseudocode

```c

```

## disassembly

```asm
0x14eac0  ldarg.0
0x14eac1  ldstr    aChartnomovedir// "ChartNoMoveDirections"
0x14eac6  ldstr    aChartnomovedir_0// "ChartNoMoveDirectionsExprHost"
0x14eacb  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::TypeStart(string typeName, string baseType)
0x14ead0  ret
```
