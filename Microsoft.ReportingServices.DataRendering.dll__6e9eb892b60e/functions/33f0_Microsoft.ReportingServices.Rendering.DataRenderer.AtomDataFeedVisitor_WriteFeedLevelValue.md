# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteFeedLevelValue

- ea: `0x33f0`
- end: `0x3425`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteFeedLevelValue`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x19c0`

## callees

- `0x33f0`
- `0xb790`

## pseudocode

```c

```

## disassembly

```asm
0x33f0  ldarg.0
0x33f1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x33f6  brtrue.s loc_3403
0x33f8  ldarg.0
0x33f9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue>::.ctor()
0x33fe  stfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3403  ldarg.0
0x3404  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x3409  ldarg.2
0x340a  ldloca.s 0
0x340c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::TryGetValue(var<u1>, !!T0)
0x3411  pop
0x3412  ldarg.0
0x3413  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3418  ldarg.1
0x3419  ldloc.0
0x341a  newobj   instance void TypedColumnValue::.ctor(string value, string edmType)
0x341f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue>::Add(var<u1>)
0x3424  ret
```
