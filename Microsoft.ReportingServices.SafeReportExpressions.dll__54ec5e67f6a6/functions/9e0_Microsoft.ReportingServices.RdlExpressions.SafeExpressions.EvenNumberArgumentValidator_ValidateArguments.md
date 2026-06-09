# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvenNumberArgumentValidator::ValidateArguments

- ea: `0x9e0`
- end: `0xa02`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvenNumberArgumentValidator::ValidateArguments`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9a0`
- `0x9e0`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.1
0x9e1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0x9e6  ldc.i4.2
0x9e7  rem
0x9e8  ldc.i4.1
0x9e9  bne.un.s loc_A01
0x9eb  ldarg.0
0x9ec  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ArgumentValidator::get_FunctionName()
0x9f1  ldstr    aRequiresAnEven// " requires an even number of arguments"
0x9f6  call     string [mscorlib]System.String::Concat(string, string)
0x9fb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa00  throw
0xa01  ret
```
