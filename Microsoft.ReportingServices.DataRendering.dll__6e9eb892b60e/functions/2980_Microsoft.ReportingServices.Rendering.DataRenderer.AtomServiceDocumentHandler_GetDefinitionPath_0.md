# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath_0

- ea: `0x2980`
- end: `0x29bb`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath_0`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2900`

## callees

- `0x2900`
- `0x2980`

## pseudocode

```c

```

## disassembly

```asm
0x2980  ldarg.0
0x2981  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class DynamicElement>::GetEnumerator()
0x2986  stloc.0
0x2987  br.s     loc_299E
0x2989  ldloca.s 0
0x298b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::get_Current()
0x2990  ldarg.1
0x2991  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::GetDefinitionPath(class DynamicElement dynamicElement, string reportItemPath)
0x2996  stloc.1
0x2997  ldloc.1
0x2998  brfalse.s loc_299E
0x299a  ldloc.1
0x299b  stloc.2
0x299c  leave.s  loc_29B9
0x299e  ldloca.s 0
0x29a0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>::MoveNext()
0x29a5  brtrue.s loc_2989
0x29a7  leave.s  loc_29B7
0x29a9  ldloca.s 0
0x29ab  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class DynamicElement>
0x29b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29b6  endfinally
0x29b7  ldnull
0x29b8  ret
0x29b9  ldloc.2
0x29ba  ret
```
