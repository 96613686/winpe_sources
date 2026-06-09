# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::Validate

- ea: `0xfe0`
- end: `0x1015`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::Validate`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xfc0`

## callees

- `0xd70`
- `0xfe0`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.0
0xfe1  ldarg.1
0xfe2  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0xfe7  stloc.0
0xfe8  ldloc.0
0xfe9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfee  brfalse.s loc_FFB
0xff0  ldstr    aEmptyOrNullIde// "Empty or null identifier name is not su"...
0xff5  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xffa  throw
0xffb  ldarg.0
0xffc  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::_vbConstantIdentifier
0x1001  ldloc.0
0x1002  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::IsIdentifierVisualBasicConstant(string identifierName)
0x1007  brfalse.s loc_100A
0x1009  ret
0x100a  ldstr    aTheSpecifiedId// "The specified identifier name is not su"...
0x100f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1014  throw
```
