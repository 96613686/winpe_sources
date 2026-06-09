# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::OneIsNull

- ea: `0x1e00`
- end: `0x1e10`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::OneIsNull`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d0`
- `0x1db0`

## callees

- `0x1e00`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.1
0x1e01  brfalse.s loc_1E06
0x1e03  ldarg.2
0x1e04  brtrue.s loc_1E0E
0x1e06  ldarg.1
0x1e07  ldarg.2
0x1e08  ceq
0x1e0a  ldc.i4.0
0x1e0b  ceq
0x1e0d  ret
0x1e0e  ldc.i4.0
0x1e0f  ret
```
