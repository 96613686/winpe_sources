# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExecutionFlowFunctions::Add

- ea: `0x770`
- end: `0x79a`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExecutionFlowFunctions::Add`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x550`

## callees

- `0x250`
- `0x5a0`
- `0x9d0`
- `0xa20`

## pseudocode

```c

```

## disassembly

```asm
0x770  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateExecutionFlowFunctionEvaluator()
0x775  stloc.0
0x776  ldarg.0
0x777  ldstr    aIif// "IIF"
0x77c  ldc.i4.3
0x77d  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x782  ldloc.0
0x783  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x788  ldarg.0
0x789  ldstr    aSwitch// "SWITCH"
0x78e  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvenNumberArgumentValidator::.ctor(string functionName)
0x793  ldloc.0
0x794  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x799  ret
```
