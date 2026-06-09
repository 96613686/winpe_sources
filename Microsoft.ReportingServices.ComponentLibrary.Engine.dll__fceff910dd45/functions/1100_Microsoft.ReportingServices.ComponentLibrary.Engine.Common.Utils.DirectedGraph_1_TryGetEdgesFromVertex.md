# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::TryGetEdgesFromVertex

- ea: `0x1100`
- end: `0x11a0`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::TryGetEdgesFromVertex`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1100`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldarg.0
0x1101  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1106  ldarg.1
0x1107  ldloca.s 0
0x1109  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::TryGetValue(var<u1>, !!T0)
0x110e  brfalse  loc_119B
0x1113  ldloca.s 0
0x1115  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_HasValue()
0x111a  brtrue.s loc_1188
0x111c  ldloca.s 0
0x111e  ldarg.0
0x111f  ldarg.1
0x1120  call     instance valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::CreateInitialEdgesFromVertex(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>)
0x1125  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::.ctor(var<u1>)
0x112a  ldarg.0
0x112b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1130  ldarg.1
0x1131  ldloc.0
0x1132  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::set_Item(var<u1>, !!T0)
0x1137  ldloca.s 0
0x1139  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x113e  stloc.1
0x113f  ldloca.s 1
0x1141  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x1146  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::get_Count()
0x114b  ldc.i4.0
0x114c  ble.s    loc_1188
0x114e  ldloca.s 0
0x1150  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x1155  stloc.1
0x1156  ldloca.s 1
0x1158  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x115d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::GetEnumerator()
0x1162  stloc.2
0x1163  br.s     loc_1174
0x1165  ldloc.2
0x1166  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x116b  stloc.3
0x116c  ldarg.0
0x116d  ldloc.3
0x116e  call     instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddVertex(var<u1>)
0x1173  pop
0x1174  ldloc.2
0x1175  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x117a  brtrue.s loc_1165
0x117c  leave.s  loc_1188
0x117e  ldloc.2
0x117f  brfalse.s loc_1187
0x1181  ldloc.2
0x1182  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1187  endfinally
0x1188  ldarg.2
0x1189  ldloca.s 0
0x118b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x1190  stloc.1
0x1191  ldloca.s 1
0x1193  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_ReadonlyObj()
0x1198  stind.ref
0x1199  ldc.i4.1
0x119a  ret
0x119b  ldarg.2
0x119c  ldnull
0x119d  stind.ref
0x119e  ldc.i4.0
0x119f  ret
```
