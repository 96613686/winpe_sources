# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.UnaryExpressionEvaluator::Evaluate

- ea: `0x1340`
- end: `0x13a1`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.UnaryExpressionEvaluator::Evaluate`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xe0`
- `0x1340`

## pseudocode

```c

```

## disassembly

```asm
0x1340  ldarg.0
0x1341  ldarg.1
0x1342  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x1347  call     instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType(object value)
0x134c  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x1351  stloc.1
0x1352  ldarg.2
0x1353  stloc.2
0x1354  ldloc.2
0x1355  ldc.i4   0x14D
0x135a  sub
0x135b  switch   loc_136E, loc_1377, loc_1380
0x136c  br.s     loc_1389
0x136e  ldloc.1
0x136f  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::PlusObject(object)
0x1374  stloc.0
0x1375  br.s     loc_139F
0x1377  ldloc.1
0x1378  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::NegateObject(object)
0x137d  stloc.0
0x137e  br.s     loc_139F
0x1380  ldloc.1
0x1381  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::NotObject(object)
0x1386  stloc.0
0x1387  br.s     loc_139F
0x1389  ldstr    aUnaryExpressio// "Unary Expression Evaluator: Syntax kind"...
0x138e  ldarg.2
0x138f  box      [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0x1394  call     string [mscorlib]System.String::Format(string, object)
0x1399  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x139e  throw
0x139f  ldloc.0
0x13a0  ret
```
