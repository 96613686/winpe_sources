# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::.ctor

- ea: `0x4f0`
- end: `0x505`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a0`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  ldarg.0
0x4f1  call     instance void [mscorlib]System.Object::.ctor()
0x4f6  ldarg.0
0x4f7  ldarg.1
0x4f8  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::_argumentValidator
0x4fd  ldarg.0
0x4fe  ldarg.2
0x4ff  stfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::_evaluator
0x504  ret
```
