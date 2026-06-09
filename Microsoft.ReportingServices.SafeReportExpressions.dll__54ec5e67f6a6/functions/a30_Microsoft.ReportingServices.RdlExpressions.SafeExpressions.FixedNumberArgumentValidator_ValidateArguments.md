# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::ValidateArguments

- ea: `0xa30`
- end: `0xa60`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::ValidateArguments`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9a0`
- `0xa30`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldarg.1
0xa31  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0xa36  ldarg.0
0xa37  ldfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FixedNumberArgumentValidator::_numberOfArguments
0xa3c  beq.s    loc_A5F
0xa3e  ldstr    a0DoesNotSuppor// "{0} does not support {1} arguments"
0xa43  ldarg.0
0xa44  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ArgumentValidator::get_FunctionName()
0xa49  ldarg.1
0xa4a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0xa4f  box      [mscorlib]System.Int32
0xa54  call     string [mscorlib]System.String::Format(string, object, object)
0xa59  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa5e  throw
0xa5f  ret
```
