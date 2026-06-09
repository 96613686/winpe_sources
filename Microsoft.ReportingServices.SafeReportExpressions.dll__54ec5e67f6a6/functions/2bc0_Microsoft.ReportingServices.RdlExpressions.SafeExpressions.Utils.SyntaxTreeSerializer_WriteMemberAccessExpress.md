# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteMemberAccessExpressionSyntaxProperties

- ea: `0x2bc0`
- end: `0x2bce`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteMemberAccessExpressionSyntaxProperties`
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
0x2bc0  ldarg.0
0x2bc1  ldarg.1
0x2bc2  ldarg.2
0x2bc3  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x2bc8  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteOperatorTokenProperty(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken operatorToken)
0x2bcd  ret
```
