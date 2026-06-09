# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InspectionFunctions::Add

- ea: `0x7b0`
- end: `0x7ff`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InspectionFunctions::Add`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x550`

## callees

- `0x270`
- `0x5a0`
- `0xa20`

## pseudocode

```c

```

## disassembly

```asm
0x7b0  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateInspectionFunctionEvaluator()
0x7b5  stloc.0
0x7b6  ldarg.0
0x7b7  ldstr    aIsarray// "ISARRAY"
0x7bc  ldc.i4.1
0x7bd  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x7c2  ldloc.0
0x7c3  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x7c8  ldarg.0
0x7c9  ldstr    aIsdate// "ISDATE"
0x7ce  ldc.i4.1
0x7cf  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x7d4  ldloc.0
0x7d5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x7da  ldarg.0
0x7db  ldstr    aIsnothing// "ISNOTHING"
0x7e0  ldc.i4.1
0x7e1  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x7e6  ldloc.0
0x7e7  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x7ec  ldarg.0
0x7ed  ldstr    aIsnumeric// "ISNUMERIC"
0x7f2  ldc.i4.1
0x7f3  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x7f8  ldloc.0
0x7f9  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x7fe  ret
```
