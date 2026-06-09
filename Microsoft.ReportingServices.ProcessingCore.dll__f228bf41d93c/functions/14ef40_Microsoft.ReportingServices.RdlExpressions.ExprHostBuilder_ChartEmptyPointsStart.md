# Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartEmptyPointsStart

- ea: `0x14ef40`
- end: `0x14ef51`
- name: `Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::ChartEmptyPointsStart`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1027c0`

## callees

- `0x152580`

## string_xrefs

- `0x14ef41`: `ChartEmptyPoints`
- `0x14ef46`: `ChartEmptyPointsExprHost`

## pseudocode

```c

```

## disassembly

```asm
0x14ef40  ldarg.0
0x14ef41  ldstr    aChartemptypoin// "ChartEmptyPoints"
0x14ef46  ldstr    aChartemptypoin_0// "ChartEmptyPointsExprHost"
0x14ef4b  call     instance void Microsoft.ReportingServices.RdlExpressions.ExprHostBuilder::TypeStart(string typeName, string baseType)
0x14ef50  ret
```
