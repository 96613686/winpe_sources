# Microsoft.ReportingServices.ReportProcessing.EventInformation::.ctor_0

- ea: `0x176b90`
- end: `0x176ca3`
- name: `Microsoft.ReportingServices.ReportProcessing.EventInformation::.ctor_0`
- size: `275`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x177290`
- `0x1779e0`
- `0x177c20`

## callees

- `0x176b90`
- `0x23e9e0`
- `0x23ecd0`
- `0x23ed00`

## string_xrefs

- `0x176b9f`: `(null != copy)`

## pseudocode

```c

```

## disassembly

```asm
0x176b90  ldarg.0
0x176b91  call     instance void [mscorlib]System.Object::.ctor()
0x176b96  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x176b9b  ldarg.1
0x176b9c  ldnull
0x176b9d  cgt.un
0x176b9f  ldstr    aNullCopy// "(null != copy)"
0x176ba4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x176ba9  ldarg.0
0x176baa  ldarg.1
0x176bab  ldfld    bool Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hasShowHideInfo
0x176bb0  stfld    bool Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hasShowHideInfo
0x176bb5  ldarg.1
0x176bb6  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_toggleStateInfo
0x176bbb  brfalse.s loc_176BD3
0x176bbd  ldarg.0
0x176bbe  ldarg.1
0x176bbf  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_toggleStateInfo
0x176bc4  callvirt instance object [mscorlib]System.Collections.Hashtable::Clone()
0x176bc9  castclass [mscorlib]System.Collections.Hashtable
0x176bce  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_toggleStateInfo
0x176bd3  ldarg.1
0x176bd4  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hiddenInfo
0x176bd9  brfalse.s loc_176BF1
0x176bdb  ldarg.0
0x176bdc  ldarg.1
0x176bdd  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hiddenInfo
0x176be2  callvirt instance object [mscorlib]System.Collections.Hashtable::Clone()
0x176be7  castclass [mscorlib]System.Collections.Hashtable
0x176bec  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hiddenInfo
0x176bf1  ldarg.0
0x176bf2  ldarg.1
0x176bf3  ldfld    bool Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hasSortInfo
0x176bf8  stfld    bool Microsoft.ReportingServices.ReportProcessing.EventInformation::m_hasSortInfo
0x176bfd  ldarg.1
0x176bfe  ldfld    class SortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_sortInfo
0x176c03  brfalse.s loc_176C18
0x176c05  ldarg.0
0x176c06  ldarg.1
0x176c07  ldfld    class SortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_sortInfo
0x176c0c  callvirt instance class SortEventInfo SortEventInfo::Clone()
0x176c11  stfld    class SortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_sortInfo
0x176c16  br.s     loc_176C31
0x176c18  ldarg.1
0x176c19  ldfld    class OdpSortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_odpSortInfo
0x176c1e  brfalse.s loc_176C31
0x176c20  ldarg.0
0x176c21  ldarg.1
0x176c22  ldfld    class OdpSortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_odpSortInfo
0x176c27  callvirt instance class OdpSortEventInfo OdpSortEventInfo::Clone()
0x176c2c  stfld    class OdpSortEventInfo Microsoft.ReportingServices.ReportProcessing.EventInformation::m_odpSortInfo
0x176c31  ldarg.1
0x176c32  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c37  brfalse.s loc_176CA2
0x176c39  ldarg.0
0x176c3a  ldarg.1
0x176c3b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c40  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation>::get_Count()
0x176c45  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation>::.ctor(int32)
0x176c4a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c4f  ldarg.1
0x176c50  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c55  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation>::get_Keys()
0x176c5a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class RendererEventInformation>::GetEnumerator()
0x176c5f  stloc.0
0x176c60  br.s     loc_176C89
0x176c62  ldloca.s 0
0x176c64  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class RendererEventInformation>::get_Current()
0x176c69  stloc.1
0x176c6a  ldarg.1
0x176c6b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c70  ldloc.1
0x176c71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation>::get_Item(void)
0x176c76  newobj   instance void RendererEventInformation::.ctor(class RendererEventInformation copy)
0x176c7b  stloc.2
0x176c7c  ldarg.0
0x176c7d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation> Microsoft.ReportingServices.ReportProcessing.EventInformation::m_rendererEventInformation
0x176c82  ldloc.1
0x176c83  ldloc.2
0x176c84  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class RendererEventInformation>::set_Item(var<u1>, !!T0)
0x176c89  ldloca.s 0
0x176c8b  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class RendererEventInformation>::MoveNext()
0x176c90  brtrue.s loc_176C62
0x176c92  leave.s  loc_176CA2
0x176c94  ldloca.s 0
0x176c96  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class RendererEventInformation>
0x176c9c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x176ca1  endfinally
0x176ca2  ret
```
