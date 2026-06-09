# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor

- ea: `0xa20`
- end: `0xa2f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d0`
- `0x770`
- `0x7b0`
- `0x810`

## callees

- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0xa20  ldarg.0
0xa21  ldarg.1
0xa22  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ArgumentValidator::.ctor(string functionName)
0xa27  ldarg.0
0xa28  ldarg.2
0xa29  stfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::_numberOfArguments
0xa2e  ret
```
