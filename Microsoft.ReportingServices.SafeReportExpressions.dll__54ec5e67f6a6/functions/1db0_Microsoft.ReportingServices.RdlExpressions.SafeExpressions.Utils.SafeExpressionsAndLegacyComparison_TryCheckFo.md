# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::TryCheckForNullValues

- ea: `0x1db0`
- end: `0x1dd3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::TryCheckForNullValues`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1710`

## callees

- `0x1db0`
- `0x1df0`
- `0x1e00`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldarg.3
0x1db1  ldc.i4.0
0x1db2  stind.i1
0x1db3  ldarg.0
0x1db4  ldarg.1
0x1db5  ldarg.2
0x1db6  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::BothAreNull(object objA, object objB)
0x1dbb  brfalse.s loc_1DC2
0x1dbd  ldarg.3
0x1dbe  ldc.i4.1
0x1dbf  stind.i1
0x1dc0  ldc.i4.1
0x1dc1  ret
0x1dc2  ldarg.0
0x1dc3  ldarg.1
0x1dc4  ldarg.2
0x1dc5  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::OneIsNull(object objA, object objB)
0x1dca  brfalse.s loc_1DD1
0x1dcc  ldarg.3
0x1dcd  ldc.i4.0
0x1dce  stind.i1
0x1dcf  ldc.i4.1
0x1dd0  ret
0x1dd1  ldc.i4.0
0x1dd2  ret
```
