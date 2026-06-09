# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::ValidateArguments

- ea: `0x510`
- end: `0x51d`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::ValidateArguments`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x940`

## pseudocode

```c

```

## disassembly

```asm
0x510  ldarg.0
0x511  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::_argumentValidator
0x516  ldarg.1
0x517  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator::ValidateArguments(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> argumentExpressions)
0x51c  ret
```
