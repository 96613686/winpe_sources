# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteUnaryExpressionSyntaxProperties

- ea: `0x2c90`
- end: `0x2c9e`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteUnaryExpressionSyntaxProperties`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2d00`

## pseudocode

```c

```

## disassembly

```asm
0x2c90  ldarg.0
0x2c91  ldarg.1
0x2c92  ldarg.2
0x2c93  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.UnaryExpressionSyntax::get_OperatorToken()
0x2c98  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOperatorTokenProperty(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken operatorToken)
0x2c9d  ret
```
