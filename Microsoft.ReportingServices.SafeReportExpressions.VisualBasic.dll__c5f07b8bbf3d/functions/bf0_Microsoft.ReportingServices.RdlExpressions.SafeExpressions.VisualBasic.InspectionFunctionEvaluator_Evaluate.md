# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.InspectionFunctionEvaluator::Evaluate

- ea: `0xbf0`
- end: `0xcaf`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.InspectionFunctionEvaluator::Evaluate`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f0`
- `0xbf0`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.0
0xbf1  ldarg.2
0xbf2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::ValidateStrongType(class [mscorlib]System.Collections.Generic.List`1<object> arguments)
0xbf7  ldarg.1
0xbf8  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xbfd  stloc.1
0xbfe  ldloc.1
0xbff  ldstr    aIsarray// "ISARRAY"
0xc04  ldc.i4.0
0xc05  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xc0a  brfalse.s loc_C38
0xc0c  ldloc.1
0xc0d  ldstr    aIsdate// "ISDATE"
0xc12  ldc.i4.0
0xc13  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xc18  brfalse.s loc_C51
0xc1a  ldloc.1
0xc1b  ldstr    aIsnothing// "ISNOTHING"
0xc20  ldc.i4.0
0xc21  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xc26  brfalse.s loc_C6A
0xc28  ldloc.1
0xc29  ldstr    aIsnumeric// "ISNUMERIC"
0xc2e  ldc.i4.0
0xc2f  call     int32 [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Operators::CompareString(string, string, bool)
0xc34  brfalse.s loc_C83
0xc36  br.s     loc_C9C
0xc38  ldarg.2
0xc39  ldc.i4.0
0xc3a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xc3f  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xc44  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.Information::IsArray(object)
0xc49  box      [mscorlib]System.Boolean
0xc4e  stloc.0
0xc4f  br.s     loc_CAD
0xc51  ldarg.2
0xc52  ldc.i4.0
0xc53  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xc58  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xc5d  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.Information::IsDate(object)
0xc62  box      [mscorlib]System.Boolean
0xc67  stloc.0
0xc68  br.s     loc_CAD
0xc6a  ldarg.2
0xc6b  ldc.i4.0
0xc6c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xc71  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xc76  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.Information::IsNothing(object)
0xc7b  box      [mscorlib]System.Boolean
0xc80  stloc.0
0xc81  br.s     loc_CAD
0xc83  ldarg.2
0xc84  ldc.i4.0
0xc85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0xc8a  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xc8f  call     bool [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Versioned::IsNumeric(object)
0xc94  box      [mscorlib]System.Boolean
0xc99  stloc.0
0xc9a  br.s     loc_CAD
0xc9c  ldstr    aFunction0IsNot// "Function <{0}> is not supported yet."
0xca1  ldarg.1
0xca2  call     string [mscorlib]System.String::Format(string, object)
0xca7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xcac  throw
0xcad  ldloc.0
0xcae  ret
```
