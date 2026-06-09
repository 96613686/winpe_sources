# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsSimpleMemberAccessExpression

- ea: `0x2b10`
- end: `0x2b2b`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsSimpleMemberAccessExpression`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ad0`

## callees

- `0x2b10`

## pseudocode

```c

```

## disassembly

```asm
0x2b10  ldarg.1
0x2b11  brtrue.s loc_2B15
0x2b13  ldc.i4.0
0x2b14  ret
0x2b15  ldarg.1
0x2b16  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax
0x2b1b  brfalse.s loc_2B29
0x2b1d  ldarg.1
0x2b1e  ldc.i4   0x123
0x2b23  call     bool [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasicExtensions::IsKind(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode, valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind)
0x2b28  ret
0x2b29  ldc.i4.0
0x2b2a  ret
```
