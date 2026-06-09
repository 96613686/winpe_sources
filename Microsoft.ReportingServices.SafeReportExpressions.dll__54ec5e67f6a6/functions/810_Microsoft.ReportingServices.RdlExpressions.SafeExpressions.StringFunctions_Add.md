# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.StringFunctions::Add

- ea: `0x810`
- end: `0x916`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.StringFunctions::Add`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x550`

## callees

- `0x260`
- `0x5a0`
- `0xa20`
- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0x810  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateStringFunctionEvaluator()
0x815  stloc.0
0x816  ldarg.0
0x817  ldstr    aAsc// "ASC"
0x81c  ldc.i4.1
0x81d  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x822  ldloc.0
0x823  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x828  ldarg.0
0x829  ldstr    aAscw// "ASCW"
0x82e  ldc.i4.1
0x82f  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x834  ldloc.0
0x835  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x83a  ldarg.0
0x83b  ldstr    aChr// "CHR"
0x840  ldc.i4.1
0x841  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x846  ldloc.0
0x847  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x84c  ldarg.0
0x84d  ldstr    aChrw// "CHRW"
0x852  ldc.i4.1
0x853  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x858  ldloc.0
0x859  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x85e  ldarg.0
0x85f  ldstr    aFormat// "FORMAT"
0x864  ldc.i4.1
0x865  ldc.i4.2
0x866  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor(string functionName, int32 minNumberOfArguments, int32 maxNumberOfArguments)
0x86b  ldloc.0
0x86c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x871  ldarg.0
0x872  ldstr    aUcase// "UCASE"
0x877  ldc.i4.1
0x878  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x87d  ldloc.0
0x87e  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x883  ldarg.0
0x884  ldstr    aLcase// "LCASE"
0x889  ldc.i4.1
0x88a  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x88f  ldloc.0
0x890  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x895  ldarg.0
0x896  ldstr    aLtrim// "LTRIM"
0x89b  ldc.i4.1
0x89c  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x8a1  ldloc.0
0x8a2  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x8a7  ldarg.0
0x8a8  ldstr    aRtrim// "RTRIM"
0x8ad  ldc.i4.1
0x8ae  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x8b3  ldloc.0
0x8b4  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x8b9  ldarg.0
0x8ba  ldstr    aTrim// "TRIM"
0x8bf  ldc.i4.1
0x8c0  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x8c5  ldloc.0
0x8c6  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x8cb  ldarg.0
0x8cc  ldstr    aJoin// "JOIN"
0x8d1  ldc.i4.1
0x8d2  ldc.i4.2
0x8d3  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor(string functionName, int32 minNumberOfArguments, int32 maxNumberOfArguments)
0x8d8  ldloc.0
0x8d9  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x8de  ldarg.0
0x8df  ldstr    aLeft// "LEFT"
0x8e4  ldc.i4.2
0x8e5  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x8ea  ldloc.0
0x8eb  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x8f0  ldarg.0
0x8f1  ldstr    aRight// "RIGHT"
0x8f6  ldc.i4.2
0x8f7  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x8fc  ldloc.0
0x8fd  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x902  ldarg.0
0x903  ldstr    aMid// "MID"
0x908  ldc.i4.2
0x909  ldc.i4.3
0x90a  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor(string functionName, int32 minNumberOfArguments, int32 maxNumberOfArguments)
0x90f  ldloc.0
0x910  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x915  ret
```
