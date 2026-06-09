# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::TraverseAndWriteCollections

- ea: `0x2800`
- end: `0x28f6`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::TraverseAndWriteCollections`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x26b0`
- `0x2800`

## callees

- `0x27d0`
- `0x2800`
- `0x2b70`

## pseudocode

```c

```

## disassembly

```asm
0x2800  ldarg.3
0x2801  ldarg.1
0x2802  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::AppendToReportItemPath(string parentReportItemPath, class DynamicElement dynamicElement)
0x2807  stloc.0
0x2808  ldarg.1
0x2809  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x280e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::get_Count()
0x2813  ldc.i4.0
0x2814  ble.s    loc_2853
0x2816  ldarg.1
0x2817  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x281c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::GetEnumerator()
0x2821  stloc.1
0x2822  br.s     loc_2837
0x2824  ldloca.s 1
0x2826  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::get_Current()
0x282b  stloc.2
0x282c  ldarg.0
0x282d  ldloc.2
0x282e  ldarg.2
0x282f  ldloc.0
0x2830  ldarg.s  4
0x2832  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::TraverseAndWriteCollections(class DynamicElement dynamicElement, string feedName, string parentReportItemPath, class [mscorlib]System.Collections.Generic.List`1<string> feedsWritten)
0x2837  ldloca.s 1
0x2839  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::MoveNext()
0x283e  brtrue.s loc_2824
0x2840  leave    loc_28F5
0x2845  ldloca.s 1
0x2847  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>
0x284d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2852  endfinally
0x2853  ldarg.2
0x2854  brtrue.s loc_285E
0x2856  ldarg.1
0x2857  ldfld    string DynamicElement::DataElementName
0x285c  starg.s  2
0x285e  ldarg.s  4
0x2860  ldarg.1
0x2861  ldfld    string DynamicElement::DefinitionPath
0x2866  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x286b  brtrue   loc_28F5
0x2870  ldarg.0
0x2871  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x2876  ldarg.2
0x2877  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x287c  brfalse.s loc_28C8
0x287e  ldarg.0
0x287f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x2884  ldarg.2
0x2885  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x288a  stloc.3
0x288b  ldarg.0
0x288c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x2891  ldarg.2
0x2892  ldloc.3
0x2893  ldc.i4.1
0x2894  add
0x2895  dup
0x2896  stloc.3
0x2897  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x289c  ldarg.2
0x289d  ldstr    asc_EEAC// "_"
0x28a2  ldloca.s 3
0x28a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28a9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x28ae  call     string [mscorlib]System.String::Concat(string, string, string)
0x28b3  stloc.s  4
0x28b5  ldarg.0
0x28b6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x28bb  ldloc.s  4
0x28bd  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x28c2  brtrue.s loc_288B
0x28c4  ldloc.s  4
0x28c6  starg.s  2
0x28c8  ldarg.0
0x28c9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_feedNames
0x28ce  ldarg.2
0x28cf  ldc.i4.0
0x28d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x28d5  ldarg.0
0x28d6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_visitor
0x28db  ldarg.1
0x28dc  ldfld    string DynamicElement::DefinitionPath
0x28e1  ldarg.2
0x28e2  ldloc.0
0x28e3  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomSchemaVisitor::WriteCollection(string definitionPath, string dataFeedName, string reportItemPath)
0x28e8  ldarg.s  4
0x28ea  ldarg.1
0x28eb  ldfld    string DynamicElement::DefinitionPath
0x28f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x28f5  ret
```
