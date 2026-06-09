# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName_0

- ea: `0x35f0`
- end: `0x365c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName_0`
- size: `108`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x16d0`
- `0x16f0`
- `0x18d0`
- `0x35e0`

## callees

- `0x35f0`
- `0x36d0`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  ldarg.0
0x35f1  ldarg.0
0x35f2  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x35f7  ldc.i4.1
0x35f8  add
0x35f9  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x35fe  ldarg.0
0x35ff  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_hasDuplicateColumnNames
0x3604  brtrue.s loc_3629
0x3606  ldarg.0
0x3607  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x360c  ldarg.1
0x360d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsValue(var<u1>)
0x3612  brtrue.s loc_3622
0x3614  ldarg.0
0x3615  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x361a  ldarg.1
0x361b  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3620  brfalse.s loc_3629
0x3622  ldarg.0
0x3623  ldc.i4.1
0x3624  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_hasDuplicateColumnNames
0x3629  ldarg.0
0x362a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x362f  ldarg.0
0x3630  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3635  ldarg.1
0x3636  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x363b  ldarg.2
0x363c  brfalse.s loc_365B
0x363e  ldarg.0
0x363f  ldarg.2
0x3640  call     instance class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GetColumnMetadata(object item)
0x3645  stloc.0
0x3646  ldloc.0
0x3647  brfalse.s loc_365B
0x3649  ldarg.0
0x364a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnMetadata
0x364f  ldarg.0
0x3650  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3655  ldloc.0
0x3656  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata>::Add(var<u1>, !!T0)
0x365b  ret
```
