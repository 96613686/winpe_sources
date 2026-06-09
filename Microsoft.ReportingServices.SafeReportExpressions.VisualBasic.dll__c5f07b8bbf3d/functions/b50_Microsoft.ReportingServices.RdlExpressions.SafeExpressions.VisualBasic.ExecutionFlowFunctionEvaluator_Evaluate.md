# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ExecutionFlowFunctionEvaluator::Evaluate

- ea: `0xb50`
- end: `0xbc9`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ExecutionFlowFunctionEvaluator::Evaluate`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f0`
- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0xb50  ldarg.0
0xb51  ldarg.2
0xb52  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::ValidateStrongType(class [mscorlib]System.Collections.Generic.List`1<object> arguments)
0xb57  ldarg.1
0xb58  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xb5d  stloc.1
0xb5e  ldloc.1
0xb5f  ldstr    aIif// "IIF"
0xb64  ldc.i4.0
0xb65  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xb6a  brfalse.s loc_B7C
0xb6c  ldloc.1
0xb6d  ldstr    aSwitch// "SWITCH"
0xb72  ldc.i4.0
0xb73  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xb78  brfalse.s loc_BA8
0xb7a  br.s     loc_BB6
0xb7c  ldarg.2
0xb7d  ldc.i4.0
0xb7e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xb83  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Conversions::ToBoolean(object)
0xb88  ldarg.2
0xb89  ldc.i4.1
0xb8a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xb8f  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xb94  ldarg.2
0xb95  ldc.i4.2
0xb96  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xb9b  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xba0  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.Interaction::IIf(bool, object, object)
0xba5  stloc.0
0xba6  br.s     loc_BC7
0xba8  ldarg.2
0xba9  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0xbae  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.Interaction::Switch(object[])
0xbb3  stloc.0
0xbb4  br.s     loc_BC7
0xbb6  ldstr    aFunction0IsNot// "Function <{0}> is not supported yet."
0xbbb  ldarg.1
0xbbc  call     string [mscorlib]System.String::Format(string, object)
0xbc1  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xbc6  throw
0xbc7  ldloc.0
0xbc8  ret
```
