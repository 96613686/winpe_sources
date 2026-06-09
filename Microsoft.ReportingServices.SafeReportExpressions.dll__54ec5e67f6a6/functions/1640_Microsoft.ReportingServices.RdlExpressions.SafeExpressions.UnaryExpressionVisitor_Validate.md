# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::Validate

- ea: `0x1640`
- end: `0x1669`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::Validate`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb50`
- `0x1640`

## pseudocode

```c

```

## disassembly

```asm
0x1640  ldarg.0
0x1641  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::_host
0x1646  ldarg.1
0x1647  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.UnaryExpressionSyntax::get_Operand()
0x164c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1651  ldarg.1
0x1652  callvirt instance valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxNode::Kind()
0x1657  stloc.0
0x1658  ldloc.0
0x1659  ldc.i4   0x14D
0x165e  sub
0x165f  ldc.i4.2
0x1660  ble.un.s loc_1668
0x1662  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x1667  throw
0x1668  ret
```
