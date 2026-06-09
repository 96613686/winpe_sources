# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Validate

- ea: `0x60`
- end: `0x78`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Validate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x60`
- `0x2b0`
- `0x3d0`

## pseudocode

```c

```

## disassembly

```asm
0x60  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::.ctor()
0x65  stloc.0
0x66  ldloc.0
0x67  ldarg.1
0x68  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x6d  leave.s  loc_74
0x6f  pop
0x70  ldc.i4.0
0x71  stloc.1
0x72  leave.s  loc_76
0x74  ldc.i4.1
0x75  ret
0x76  ldloc.1
0x77  ret
```
