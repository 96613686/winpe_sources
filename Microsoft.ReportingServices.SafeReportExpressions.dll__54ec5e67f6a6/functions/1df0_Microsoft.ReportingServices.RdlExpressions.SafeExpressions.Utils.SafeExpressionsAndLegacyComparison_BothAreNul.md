# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::BothAreNull

- ea: `0x1df0`
- end: `0x1dfa`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::BothAreNull`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1db0`

## callees

- `0x1df0`

## pseudocode

```c

```

## disassembly

```asm
0x1df0  ldarg.1
0x1df1  brtrue.s loc_1DF8
0x1df3  ldarg.2
0x1df4  ldnull
0x1df5  ceq
0x1df7  ret
0x1df8  ldc.i4.0
0x1df9  ret
```
