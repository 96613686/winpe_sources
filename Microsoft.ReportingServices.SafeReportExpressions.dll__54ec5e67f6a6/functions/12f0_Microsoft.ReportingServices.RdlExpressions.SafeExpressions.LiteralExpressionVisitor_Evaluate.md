# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.LiteralExpressionVisitor::Evaluate

- ea: `0x12f0`
- end: `0x130e`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.LiteralExpressionVisitor::Evaluate`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x12f0`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.1
0x12f1  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.LiteralExpressionSyntax::get_Token()
0x12f6  stloc.0
0x12f7  ldloca.s 0
0x12f9  call     instance bool [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_ContainsDiagnostics()
0x12fe  brfalse.s loc_1306
0x1300  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x1305  throw
0x1306  ldloca.s 0
0x1308  call     instance object [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Value()
0x130d  ret
```
