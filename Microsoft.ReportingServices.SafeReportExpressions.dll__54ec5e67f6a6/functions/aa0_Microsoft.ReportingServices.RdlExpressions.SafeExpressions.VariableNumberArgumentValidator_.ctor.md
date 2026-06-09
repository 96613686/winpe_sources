# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor

- ea: `0xaa0`
- end: `0xab6`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d0`
- `0x810`

## callees

- `0x990`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  ldarg.1
0xaa2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ArgumentValidator::.ctor(string functionName)
0xaa7  ldarg.0
0xaa8  ldarg.2
0xaa9  stfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::_minNumberOfArguments
0xaae  ldarg.0
0xaaf  ldarg.3
0xab0  stfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::_maxNumberOfArguments
0xab5  ret
```
