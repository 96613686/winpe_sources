# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteBinaryExpressionSyntaxProperties

- ea: `0x2bb0`
- end: `0x2bbe`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteBinaryExpressionSyntaxProperties`
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
0x2bb0  ldarg.0
0x2bb1  ldarg.1
0x2bb2  ldarg.2
0x2bb3  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax::get_OperatorToken()
0x2bb8  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOperatorTokenProperty(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken operatorToken)
0x2bbd  ret
```
