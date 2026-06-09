# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::.ctor_0

- ea: `0x2c0`
- end: `0x2d6`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::.ctor_0`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x40`
- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldarg.0
0x2c1  ldc.i4.0
0x2c2  call     instance void [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxWalker::.ctor(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxWalkerDepth)
0x2c7  ldarg.0
0x2c8  ldarg.1
0x2c9  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_reportContext
0x2ce  ldarg.0
0x2cf  ldnull
0x2d0  stfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_result
0x2d5  ret
```
