# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch

- ea: `0x19c0`
- end: `0x19d0`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1710`

## callees

- `0x19c0`
- `0x1e10`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.1
0x19c1  callvirt instance var<u1> class [mscorlib]System.Func`1<bool>::Invoke()
0x19c6  dup
0x19c7  brtrue.s loc_19CF
0x19c9  ldarg.0
0x19ca  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchDetails()
0x19cf  ret
```
