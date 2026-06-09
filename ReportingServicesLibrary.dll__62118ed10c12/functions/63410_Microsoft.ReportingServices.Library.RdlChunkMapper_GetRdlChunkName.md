# Microsoft.ReportingServices.Library.RdlChunkMapper::GetRdlChunkName

- ea: `0x63410`
- end: `0x63509`
- name: `Microsoft.ReportingServices.Library.RdlChunkMapper::GetRdlChunkName`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x17210`
- `0x6a3f0`

## callees

- `0x63410`
- `0x8c0b0`

## string_xrefs

- `0x63431`: `chunk names already persisted`
- `0x6346c`: `main report already defined`

## pseudocode

```c

```

## disassembly

```asm
0x63410  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x63415  ldarg.1
0x63416  ldnull
0x63417  cgt.un
0x63419  ldstr    aReportcontext// "reportContext"
0x6341e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x63423  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x63428  ldarg.0
0x63429  ldfld    bool Microsoft.ReportingServices.Library.RdlChunkMapper::m_chunkNamesPersisted
0x6342e  ldc.i4.0
0x6342f  ceq
0x63431  ldstr    aChunkNamesAlre// "chunk names already persisted"
0x63436  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6343b  ldarg.1
0x6343c  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x63441  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x63446  stloc.0
0x63447  ldarg.0
0x63448  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData> Microsoft.ReportingServices.Library.RdlChunkMapper::m_rdlChunkNames
0x6344d  stloc.2
0x6344e  ldc.i4.0
0x6344f  stloc.3
0x63450  ldloc.2
0x63451  ldloca.s 3
0x63453  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x63458  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6345d  ldarg.2
0x6345e  brfalse.s loc_6346B
0x63460  ldarg.0
0x63461  ldfld    bool Microsoft.ReportingServices.Library.RdlChunkMapper::m_mainReportStored
0x63466  ldc.i4.0
0x63467  ceq
0x63469  br.s     loc_6346C
0x6346b  ldc.i4.1
0x6346c  ldstr    aMainReportAlre// "main report already defined"
0x63471  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x63476  ldarg.3
0x63477  ldarg.0
0x63478  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData> Microsoft.ReportingServices.Library.RdlChunkMapper::m_rdlChunkNames
0x6347d  ldloc.0
0x6347e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData>::ContainsKey(var<u1>)
0x63483  ldc.i4.0
0x63484  ceq
0x63486  stind.i1
0x63487  ldarg.3
0x63488  ldind.u1
0x63489  brfalse.s loc_634B5
0x6348b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x63490  stloc.s  4
0x63492  ldloca.s 4
0x63494  constrained. [mscorlib]System.Guid
0x6349a  callvirt instance string [mscorlib]System.Object::ToString()
0x6349f  stloc.1
0x634a0  ldarg.0
0x634a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData> Microsoft.ReportingServices.Library.RdlChunkMapper::m_rdlChunkNames
0x634a6  ldloc.0
0x634a7  ldloc.1
0x634a8  ldarg.2
0x634a9  newobj   instance void ChunkData::.ctor(string name, bool isMainReport)
0x634ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData>::Add(var<u1>, !!T0)
0x634b3  br.s     loc_634D5
0x634b5  ldarg.0
0x634b6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData> Microsoft.ReportingServices.Library.RdlChunkMapper::m_rdlChunkNames
0x634bb  ldloc.0
0x634bc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ChunkData>::get_Item(void)
0x634c1  dup
0x634c2  dup
0x634c3  ldfld    bool ChunkData::IsMainReport
0x634c8  ldarg.2
0x634c9  or
0x634ca  stfld    bool ChunkData::IsMainReport
0x634cf  ldfld    string ChunkData::Name
0x634d4  stloc.1
0x634d5  ldarg.0
0x634d6  ldarg.0
0x634d7  ldfld    bool Microsoft.ReportingServices.Library.RdlChunkMapper::m_mainReportStored
0x634dc  ldarg.2
0x634dd  or
0x634de  stfld    bool Microsoft.ReportingServices.Library.RdlChunkMapper::m_mainReportStored
0x634e3  leave.s  loc_634EF
0x634e5  ldloc.3
0x634e6  brfalse.s loc_634EE
0x634e8  ldloc.2
0x634e9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x634ee  endfinally
0x634ef  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x634f4  ldloc.1
0x634f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x634fa  ldc.i4.0
0x634fb  ceq
0x634fd  ldstr    aChunkname_0// "chunkName"
0x63502  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x63507  ldloc.1
0x63508  ret
```
