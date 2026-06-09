# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::SetResolvedEdmTypes

- ea: `0x3660`
- end: `0x36c3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::SetResolvedEdmTypes`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`

## callees

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x3660  ldarg.0
0x3661  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x3666  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_resolvedColumnEdmTypes
0x366b  ldarg.1
0x366c  brtrue.s loc_366F
0x366e  ret
0x366f  ldc.i4.1
0x3670  stloc.0
0x3671  ldarg.0
0x3672  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3677  brfalse.s loc_3687
0x3679  ldloc.0
0x367a  ldarg.0
0x367b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3680  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue>::get_Count()
0x3685  add
0x3686  stloc.0
0x3687  ldarg.1
0x3688  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x368d  stloc.1
0x368e  br.s     loc_36A9
0x3690  ldloca.s 1
0x3692  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x3697  stloc.2
0x3698  ldarg.0
0x3699  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_resolvedColumnEdmTypes
0x369e  ldloc.0
0x369f  ldloc.2
0x36a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x36a5  ldloc.0
0x36a6  ldc.i4.1
0x36a7  add
0x36a8  stloc.0
0x36a9  ldloca.s 1
0x36ab  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x36b0  brtrue.s loc_3690
0x36b2  leave.s  loc_36C2
0x36b4  ldloca.s 1
0x36b6  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x36bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36c1  endfinally
0x36c2  ret
```
