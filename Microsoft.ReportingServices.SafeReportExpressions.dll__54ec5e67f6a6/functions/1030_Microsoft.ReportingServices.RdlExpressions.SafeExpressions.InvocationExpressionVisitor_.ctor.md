# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::.ctor

- ea: `0x1030`
- end: `0x10c3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::.ctor`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x360`

## callees

- `0x550`
- `0x1690`

## pseudocode

```c

```

## disassembly

```asm
0x1030  ldarg.0
0x1031  ldc.i4.s 0xD
0x1033  newarr   [mscorlib]System.String
0x1038  dup
0x1039  ldc.i4.0
0x103a  ldstr    aAvg// "AVG"
0x103f  stelem.ref
0x1040  dup
0x1041  ldc.i4.1
0x1042  ldstr    aCount// "COUNT"
0x1047  stelem.ref
0x1048  dup
0x1049  ldc.i4.2
0x104a  ldstr    aCountdistinct// "COUNTDISTINCT"
0x104f  stelem.ref
0x1050  dup
0x1051  ldc.i4.3
0x1052  ldstr    aCountrows// "COUNTROWS"
0x1057  stelem.ref
0x1058  dup
0x1059  ldc.i4.4
0x105a  ldstr    aFirst// "FIRST"
0x105f  stelem.ref
0x1060  dup
0x1061  ldc.i4.5
0x1062  ldstr    aLast// "LAST"
0x1067  stelem.ref
0x1068  dup
0x1069  ldc.i4.6
0x106a  ldstr    aMax// "MAX"
0x106f  stelem.ref
0x1070  dup
0x1071  ldc.i4.7
0x1072  ldstr    aMin// "MIN"
0x1077  stelem.ref
0x1078  dup
0x1079  ldc.i4.8
0x107a  ldstr    aStdev// "STDEV"
0x107f  stelem.ref
0x1080  dup
0x1081  ldc.i4.s 9
0x1083  ldstr    aStdevp// "STDEVP"
0x1088  stelem.ref
0x1089  dup
0x108a  ldc.i4.s 0xA
0x108c  ldstr    aSum// "SUM"
0x1091  stelem.ref
0x1092  dup
0x1093  ldc.i4.s 0xB
0x1095  ldstr    aVar// "VAR"
0x109a  stelem.ref
0x109b  dup
0x109c  ldc.i4.s 0xC
0x109e  ldstr    aVarp// "VARP"
0x10a3  stelem.ref
0x10a4  stfld    string[] Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::BuiltInFunctionArgIdentifiers
0x10a9  ldarg.0
0x10aa  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::.ctor()
0x10af  ldarg.0
0x10b0  ldarg.1
0x10b1  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_host
0x10b6  ldarg.0
0x10b7  ldarg.2
0x10b8  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x10bd  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_functionFactory
0x10c2  ret
```
