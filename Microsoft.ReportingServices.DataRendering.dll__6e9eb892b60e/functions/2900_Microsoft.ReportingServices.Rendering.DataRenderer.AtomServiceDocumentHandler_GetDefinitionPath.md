# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath

- ea: `0x2900`
- end: `0x2976`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x2980`

## callees

- `0x2900`
- `0x2980`
- `0xb760`

## pseudocode

```c

```

## disassembly

```asm
0x2900  ldarg.0
0x2901  callvirt instance bool DynamicElement::IsRoot()
0x2906  brfalse.s loc_2915
0x2908  ldarg.0
0x2909  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x290e  ldarg.1
0x290f  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath(class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> dynamicElements, string reportItemPath)
0x2914  ret
0x2915  ldarg.0
0x2916  ldfld    string DynamicElement::ReportItemName
0x291b  brfalse.s loc_2925
0x291d  ldarg.0
0x291e  ldfld    string DynamicElement::ReportItemName
0x2923  br.s     loc_292A
0x2925  ldsfld   string [mscorlib]System.String::Empty
0x292a  stloc.0
0x292b  ldarg.1
0x292c  ldloc.0
0x292d  ldc.i4.4
0x292e  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2933  brfalse.s loc_2974
0x2935  ldarg.1
0x2936  callvirt instance int32 [mscorlib]System.String::get_Length()
0x293b  ldloc.0
0x293c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2941  bne.un.s loc_294A
0x2943  ldarg.0
0x2944  ldfld    string DynamicElement::DefinitionPath
0x2949  ret
0x294a  ldarg.1
0x294b  ldloc.0
0x294c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2951  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2956  ldc.i4.s 0x2E
0x2958  bne.un.s loc_2974
0x295a  ldarg.0
0x295b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> DynamicElement::Children
0x2960  ldarg.1
0x2961  ldloc.0
0x2962  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2967  ldc.i4.1
0x2968  add
0x2969  callvirt instance string [mscorlib]System.String::Substring(int32)
0x296e  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath(class [mscorlib]System.Collections.Generic.List`1<class DynamicElement> dynamicElements, string reportItemPath)
0x2973  ret
0x2974  ldnull
0x2975  ret
```
