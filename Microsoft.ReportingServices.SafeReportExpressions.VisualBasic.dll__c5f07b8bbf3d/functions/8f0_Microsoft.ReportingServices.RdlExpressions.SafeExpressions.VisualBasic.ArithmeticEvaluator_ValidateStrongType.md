# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::ValidateStrongType

- ea: `0x8f0`
- end: `0x92d`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::ValidateStrongType`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb50`
- `0xbf0`
- `0xd30`

## callees

- `0xe0`
- `0x8f0`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.1
0x8f1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<object>::GetEnumerator()
0x8f6  stloc.0
0x8f7  br.s     loc_913
0x8f9  ldloca.s 0
0x8fb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<object>::get_Current()
0x900  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x905  stloc.1
0x906  ldarg.0
0x907  ldloc.1
0x908  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x90d  call     instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ArithmeticEvaluator::CastToStrongType(object value)
0x912  pop
0x913  ldloca.s 0
0x915  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<object>::MoveNext()
0x91a  brtrue.s loc_8F9
0x91c  leave.s  loc_92C
0x91e  ldloca.s 0
0x920  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<object>
0x926  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x92b  endfinally
0x92c  ret
```
