# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::GetSimpleNameText

- ea: `0x14d0`
- end: `0x14df`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::GetSimpleNameText`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1420`

## pseudocode

```c

```

## disassembly

```asm
0x14d0  ldarg.1
0x14d1  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.SimpleNameSyntax::get_Identifier()
0x14d6  stloc.0
0x14d7  ldloca.s 0
0x14d9  call     instance string [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken::get_Text()
0x14de  ret
```
