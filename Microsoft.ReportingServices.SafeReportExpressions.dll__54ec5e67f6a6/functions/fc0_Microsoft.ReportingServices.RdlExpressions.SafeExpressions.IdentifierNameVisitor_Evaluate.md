# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::Evaluate

- ea: `0xfc0`
- end: `0xfdc`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::Evaluate`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xfe0`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0xfc0  ldarg.0
0xfc1  ldarg.1
0xfc2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax node)
0xfc7  ldarg.0
0xfc8  ldarg.1
0xfc9  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0xfce  stloc.0
0xfcf  ldarg.0
0xfd0  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IVisualBasicConstantEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::_vbConstantIdentifierEvaluator
0xfd5  ldloc.0
0xfd6  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IVisualBasicConstantEvaluator::EvaluateConstant(string)
0xfdb  ret
```
