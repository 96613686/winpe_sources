# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::WriteCollection

- ea: `0x26b0`
- end: `0x272e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::WriteCollection`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1cf0`
- `0x1e90`

## callees

- `0x26b0`
- `0x2730`
- `0x2800`

## string_xrefs

- `0x26db`: `AtomServiceDocument.WriteCollection: There is more than one top level dynamic element`

## pseudocode

```c

```

## disassembly

```asm
0x26b0  ldarg.0
0x26b1  ldfld    class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementRoot
0x26b6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x26bb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::get_Count()
0x26c0  ldc.i4.0
0x26c1  ble.s    loc_272D
0x26c3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x26c8  ldarg.0
0x26c9  ldfld    class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementRoot
0x26ce  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x26d3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::get_Count()
0x26d8  ldc.i4.1
0x26d9  ceq
0x26db  ldstr    aAtomservicedoc// "AtomServiceDocument.WriteCollection: Th"...
0x26e0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26e5  ldarg.0
0x26e6  ldfld    class DynamicElement Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementRoot
0x26eb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x26f0  ldc.i4.0
0x26f1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::get_Item(!!T0)
0x26f6  stloc.0
0x26f7  ldnull
0x26f8  stloc.1
0x26f9  ldarg.0
0x26fa  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_multipleFeeds
0x26ff  brtrue.s loc_2708
0x2701  ldloc.0
0x2702  ldfld    string DynamicElement::DataElementName
0x2707  stloc.1
0x2708  ldnull
0x2709  stloc.2
0x270a  ldarg.1
0x270b  brfalse.s loc_271D
0x270d  ldarg.0
0x270e  ldarg.1
0x270f  ldloc.0
0x2710  ldfld    string DynamicElement::DefinitionPath
0x2715  ldloca.s 2
0x2717  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetScopeElementReportItemPath(class DynamicElement scopeElement, string definitionPath, string& reportItemPath)
0x271c  pop
0x271d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2722  stloc.3
0x2723  ldarg.0
0x2724  ldloc.0
0x2725  ldloc.1
0x2726  ldloc.2
0x2727  ldloc.3
0x2728  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::TraverseAndWriteCollections(class DynamicElement dynamicElement, string feedName, string parentReportItemPath, class [mscorlib]System.Collections.Generic.List`1<string> feedsWritten)
0x272d  ret
```
