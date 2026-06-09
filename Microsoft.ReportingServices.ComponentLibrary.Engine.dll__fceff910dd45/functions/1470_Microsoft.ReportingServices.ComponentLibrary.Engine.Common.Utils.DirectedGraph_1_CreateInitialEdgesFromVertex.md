# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::CreateInitialEdgesFromVertex

- ea: `0x1470`
- end: `0x1483`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::CreateInitialEdgesFromVertex`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1470  ldarg.0
0x1471  ldarg.1
0x1472  callvirt instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::CreateInitialEdgesFromVertexOverride(!!T0)
0x1477  dup
0x1478  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x147d  newobj   instance void valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::.ctor(var<u1>, !!T0)
0x1482  ret
```
