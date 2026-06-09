# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::ValidateArguments

- ea: `0xac0`
- end: `0xafe`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::ValidateArguments`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x9a0`
- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xac0  ldarg.1
0xac1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0xac6  ldarg.0
0xac7  ldfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::_minNumberOfArguments
0xacc  blt.s    loc_ADC
0xace  ldarg.1
0xacf  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0xad4  ldarg.0
0xad5  ldfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VariableNumberArgumentValidator::_maxNumberOfArguments
0xada  ble.s    loc_AFD
0xadc  ldstr    a0DoesNotSuppor// "{0} does not support {1} arguments"
0xae1  ldarg.0
0xae2  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ArgumentValidator::get_FunctionName()
0xae7  ldarg.1
0xae8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Count()
0xaed  box      [mscorlib]System.Int32
0xaf2  call     string [mscorlib]System.String::Format(string, object, object)
0xaf7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xafc  throw
0xafd  ret
```
