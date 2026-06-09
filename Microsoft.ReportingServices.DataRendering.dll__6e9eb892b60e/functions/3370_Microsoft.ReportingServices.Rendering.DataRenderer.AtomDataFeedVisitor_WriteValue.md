# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue

- ea: `0x3370`
- end: `0x33e3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue`
- size: `115`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1180`
- `0x1250`
- `0x12e0`
- `0x1530`
- `0x15c0`
- `0x1630`
- `0x1670`

## callees

- `0x32a0`
- `0x3370`
- `0x3d70`

## pseudocode

```c

```

## disassembly

```asm
0x3370  ldarg.0
0x3371  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0x3376  brtrue.s loc_337E
0x3378  ldarg.0
0x3379  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateNewSyndicationItem()
0x337e  ldarg.0
0x337f  ldarg.0
0x3380  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3385  ldc.i4.1
0x3386  add
0x3387  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x338c  ldarg.0
0x338d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x3392  ldarg.0
0x3393  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3398  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x339d  stloc.0
0x339e  ldarg.0
0x339f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_resolvedColumnEdmTypes
0x33a4  ldarg.0
0x33a5  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x33aa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0x33af  brfalse.s loc_33C5
0x33b1  ldarg.0
0x33b2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_resolvedColumnEdmTypes
0x33b7  ldarg.0
0x33b8  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x33bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x33c2  stloc.1
0x33c3  br.s     loc_33D4
0x33c5  ldarg.0
0x33c6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x33cb  ldarg.2
0x33cc  ldloca.s 1
0x33ce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::TryGetValue(var<u1>, !!T0)
0x33d3  pop
0x33d4  ldarg.0
0x33d5  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_rowContent
0x33da  ldloc.0
0x33db  ldloc.1
0x33dc  ldarg.1
0x33dd  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::Add(string columnName, string edmType, string value)
0x33e2  ret
```
