# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::NeitherIsNull

- ea: `0x1de0`
- end: `0x1dea`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::NeitherIsNull`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d0`
- `0x1e10`

## callees

- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldarg.1
0x1de1  brfalse.s loc_1DE8
0x1de3  ldarg.2
0x1de4  ldnull
0x1de5  cgt.un
0x1de7  ret
0x1de8  ldc.i4.0
0x1de9  ret
```
