# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctions::Add

- ea: `0x5d0`
- end: `0x751`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctions::Add`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x550`

## callees

- `0x410`
- `0x5a0`
- `0xa20`
- `0xa70`
- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.1
0x5d1  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x5d6  stloc.0
0x5d7  ldarg.0
0x5d8  ldstr    aAvg// "AVG"
0x5dd  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x5e2  ldnull
0x5e3  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x5e8  ldarg.0
0x5e9  ldstr    aCount// "COUNT"
0x5ee  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x5f3  ldnull
0x5f4  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x5f9  ldarg.0
0x5fa  ldstr    aCountdistinct// "COUNTDISTINCT"
0x5ff  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x604  ldnull
0x605  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x60a  ldarg.0
0x60b  ldstr    aCountrows// "COUNTROWS"
0x610  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x615  ldnull
0x616  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x61b  ldarg.0
0x61c  ldstr    aFirst// "FIRST"
0x621  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x626  ldnull
0x627  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x62c  ldarg.0
0x62d  ldstr    aLast// "LAST"
0x632  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x637  ldnull
0x638  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x63d  ldarg.0
0x63e  ldstr    aMax// "MAX"
0x643  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x648  ldnull
0x649  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x64e  ldarg.0
0x64f  ldstr    aMin// "MIN"
0x654  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x659  ldnull
0x65a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x65f  ldarg.0
0x660  ldstr    aStdev// "STDEV"
0x665  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x66a  ldnull
0x66b  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x670  ldarg.0
0x671  ldstr    aStdevp// "STDEVP"
0x676  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x67b  ldnull
0x67c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x681  ldarg.0
0x682  ldstr    aSum// "SUM"
0x687  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x68c  ldnull
0x68d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x692  ldarg.0
0x693  ldstr    aVar// "VAR"
0x698  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x69d  ldnull
0x69e  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6a3  ldarg.0
0x6a4  ldstr    aVarp// "VARP"
0x6a9  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x6ae  ldnull
0x6af  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6b4  ldarg.0
0x6b5  ldstr    aRunningvalue// "RUNNINGVALUE"
0x6ba  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x6bf  ldnull
0x6c0  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6c5  ldarg.0
0x6c6  ldstr    aAggregate// "AGGREGATE"
0x6cb  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x6d0  ldnull
0x6d1  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6d6  ldarg.0
0x6d7  ldstr    aInscope// "INSCOPE"
0x6dc  ldc.i4.1
0x6dd  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::.ctor(string functionName, int32 numberOfArguments)
0x6e2  ldloc.0
0x6e3  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6e8  ldarg.0
0x6e9  ldstr    aLevel// "LEVEL"
0x6ee  ldc.i4.0
0x6ef  ldc.i4.1
0x6f0  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::.ctor(string functionName, int32 minNumberOfArguments, int32 maxNumberOfArguments)
0x6f5  ldloc.0
0x6f6  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x6fb  ldarg.0
0x6fc  ldstr    aLookup// "LOOKUP"
0x701  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x706  ldnull
0x707  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x70c  ldarg.0
0x70d  ldstr    aLookupset// "LOOKUPSET"
0x712  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x717  ldnull
0x718  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x71d  ldarg.0
0x71e  ldstr    aMultilookup// "MULTILOOKUP"
0x723  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x728  ldnull
0x729  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x72e  ldarg.0
0x72f  ldstr    aPrevious// "PREVIOUS"
0x734  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x739  ldnull
0x73a  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x73f  ldarg.0
0x740  ldstr    aRownumber// "ROWNUMBER"
0x745  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.NoValidationArgumentValidator::.ctor(string functionName)
0x74a  ldnull
0x74b  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x750  ret
```
