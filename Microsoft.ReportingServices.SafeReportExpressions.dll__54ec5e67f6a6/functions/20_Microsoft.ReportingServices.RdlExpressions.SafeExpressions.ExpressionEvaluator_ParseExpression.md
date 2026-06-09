# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ParseExpression

- ea: `0x20`
- end: `0x37`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ParseExpression`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x80`

## pseudocode

```c

```

## disassembly

```asm
0x20  ldarg.0
0x21  ldarg.1
0x22  callvirt instance string [mscorlib]System.String::Trim()
0x27  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ConvertFirstDateLiteralToTernary(string expression)
0x2c  starg.s  1
0x2e  ldarg.1
0x2f  ldc.i4.0
0x30  ldc.i4.1
0x31  call     class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxFactory::ParseExpression(string, int32, bool)
0x36  ret
```
