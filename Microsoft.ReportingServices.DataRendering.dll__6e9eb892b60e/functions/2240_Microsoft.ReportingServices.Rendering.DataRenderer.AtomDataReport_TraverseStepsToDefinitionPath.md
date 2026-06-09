# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::TraverseStepsToDefinitionPath

- ea: `0x2240`
- end: `0x22b9`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::TraverseStepsToDefinitionPath`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2200`
- `0x2240`

## callees

- `0x2240`

## pseudocode

```c

```

## disassembly

```asm
0x2240  ldarg.1
0x2241  ldfld    string DynamicElement::DefinitionPath
0x2246  ldarg.2
0x2247  call     bool [mscorlib]System.String::op_Equality(string, string)
0x224c  brfalse.s loc_225C
0x224e  ldarg.3
0x224f  ldarg.1
0x2250  ldfld    string DynamicElement::DefinitionPath
0x2255  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x225a  ldc.i4.1
0x225b  ret
0x225c  ldarg.1
0x225d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x2262  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::get_Count()
0x2267  ldc.i4.0
0x2268  ble.s    loc_22B5
0x226a  ldarg.1
0x226b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x2270  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::GetEnumerator()
0x2275  stloc.0
0x2276  br.s     loc_229C
0x2278  ldloca.s 0
0x227a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::get_Current()
0x227f  stloc.1
0x2280  ldarg.0
0x2281  ldloc.1
0x2282  ldarg.2
0x2283  ldarg.3
0x2284  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::TraverseStepsToDefinitionPath(class DynamicElement dynamicElement, string definitionPath, class [mscorlib]System.Collections.Generic.List`1<string> steps)
0x2289  brfalse.s loc_229C
0x228b  ldarg.3
0x228c  ldc.i4.0
0x228d  ldarg.1
0x228e  ldfld    string DynamicElement::DefinitionPath
0x2293  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Insert(int32, var<u1>)
0x2298  ldc.i4.1
0x2299  stloc.2
0x229a  leave.s  loc_22B7
0x229c  ldloca.s 0
0x229e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::MoveNext()
0x22a3  brtrue.s loc_2278
0x22a5  leave.s  loc_22B5
0x22a7  ldloca.s 0
0x22a9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>
0x22af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22b4  endfinally
0x22b5  ldc.i4.0
0x22b6  ret
0x22b7  ldloc.2
0x22b8  ret
```
