# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetScopeElementReportItemPath

- ea: `0x2730`
- end: `0x27ac`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetScopeElementReportItemPath`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x26b0`
- `0x2730`

## callees

- `0x2730`
- `0xb760`

## pseudocode

```c

```

## disassembly

```asm
0x2730  ldarg.1
0x2731  ldfld    string DynamicElement::DefinitionPath
0x2736  ldarg.2
0x2737  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273c  brfalse.s loc_2740
0x273e  ldc.i4.1
0x273f  ret
0x2740  ldarg.1
0x2741  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x2746  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::GetEnumerator()
0x274b  stloc.0
0x274c  br.s     loc_278F
0x274e  ldloca.s 0
0x2750  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::get_Current()
0x2755  stloc.1
0x2756  ldarg.0
0x2757  ldloc.1
0x2758  ldarg.2
0x2759  ldarg.3
0x275a  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetScopeElementReportItemPath(class DynamicElement scopeElement, string definitionPath, string& reportItemPath)
0x275f  brfalse.s loc_278F
0x2761  ldarg.1
0x2762  callvirt instance bool DynamicElement::IsRoot()
0x2767  brtrue.s loc_278B
0x2769  ldarg.3
0x276a  ldind.ref
0x276b  brtrue.s loc_2777
0x276d  ldarg.3
0x276e  ldarg.1
0x276f  ldfld    string DynamicElement::ReportItemName
0x2774  stind.ref
0x2775  br.s     loc_278B
0x2777  ldarg.3
0x2778  ldarg.1
0x2779  ldfld    string DynamicElement::ReportItemName
0x277e  ldstr    asc_EEA8// "."
0x2783  ldarg.3
0x2784  ldind.ref
0x2785  call     string [mscorlib]System.String::Concat(string, string, string)
0x278a  stind.ref
0x278b  ldc.i4.1
0x278c  stloc.2
0x278d  leave.s  loc_27AA
0x278f  ldloca.s 0
0x2791  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::MoveNext()
0x2796  brtrue.s loc_274E
0x2798  leave.s  loc_27A8
0x279a  ldloca.s 0
0x279c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>
0x27a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27a7  endfinally
0x27a8  ldc.i4.0
0x27a9  ret
0x27aa  ldloc.2
0x27ab  ret
```
