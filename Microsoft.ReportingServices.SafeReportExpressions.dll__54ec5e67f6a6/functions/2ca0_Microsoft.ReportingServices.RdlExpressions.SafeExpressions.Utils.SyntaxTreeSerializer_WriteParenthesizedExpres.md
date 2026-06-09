# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteParenthesizedExpressionSyntaxProperties

- ea: `0x2ca0`
- end: `0x2cb4`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteParenthesizedExpressionSyntaxProperties`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a10`

## callees

- `0x2d20`

## pseudocode

```c

```

## disassembly

```asm
0x2ca0  ldarg.0
0x2ca1  ldarg.1
0x2ca2  ldarg.2
0x2ca3  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax::get_OpenParenToken()
0x2ca8  ldarg.2
0x2ca9  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax::get_CloseParenToken()
0x2cae  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOpenCloseParanTokenProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken openParanToken, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken closeParanToken)
0x2cb3  ret
```
