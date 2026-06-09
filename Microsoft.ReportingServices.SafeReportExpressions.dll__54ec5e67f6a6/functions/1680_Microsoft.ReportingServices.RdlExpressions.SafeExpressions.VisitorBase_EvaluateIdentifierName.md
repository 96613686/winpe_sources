# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName

- ea: `0x1680`
- end: `0x168f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName`
- size: `15`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xfc0`
- `0xfe0`
- `0x10d0`
- `0x1100`
- `0x11b0`
- `0x1370`
- `0x1420`

## pseudocode

```c

```

## disassembly

```asm
0x1680  ldarg.1
0x1681  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax::get_Identifier()
0x1686  stloc.0
0x1687  ldloca.s 0
0x1689  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x168e  ret
```
