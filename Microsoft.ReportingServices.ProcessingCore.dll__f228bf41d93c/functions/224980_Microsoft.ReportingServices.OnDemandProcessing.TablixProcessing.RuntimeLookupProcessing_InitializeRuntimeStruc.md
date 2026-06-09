# Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::InitializeRuntimeStructures

- ea: `0x224980`
- end: `0x224a55`
- name: `Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::InitializeRuntimeStructures`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x224940`

## callees

- `0xd8860`
- `0x114e00`
- `0x11cac0`
- `0x11ce60`
- `0x11d320`
- `0x1fb6d0`
- `0x1fb960`
- `0x1fb980`
- `0x2103d0`
- `0x224980`

## string_xrefs

- `0x2249a8`: `Attempted to perform Lookup processing on a DataSet with no Lookups`

## pseudocode

```c

```

## disassembly

```asm
0x224980  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x224985  ldarg.0
0x224986  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_dataSet
0x22498b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo> Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_LookupDestinationInfos()
0x224990  brfalse.s loc_2249A7
0x224992  ldarg.0
0x224993  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_dataSet
0x224998  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo> Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_LookupDestinationInfos()
0x22499d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo>::get_Count()
0x2249a2  ldc.i4.0
0x2249a3  cgt
0x2249a5  br.s     loc_2249A8
0x2249a7  ldc.i4.0
0x2249a8  ldstr    aAttemptedToPer// "Attempted to perform Lookup processing "...
0x2249ad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2249b2  ldarg.0
0x2249b3  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_odpContext
0x2249b8  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalabilityCache Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_TablixProcessingScalabilityCache()
0x2249bd  stloc.0
0x2249be  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2249c3  ldloc.0
0x2249c4  ldnull
0x2249c5  cgt.un
0x2249c7  ldstr    aCannotStartLoo// "Cannot start Lookup processing unless S"...
0x2249cc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2249d1  ldarg.0
0x2249d2  ldfld    bool Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_mustBufferAllRows
0x2249d7  brfalse.s loc_2249EA
0x2249d9  ldarg.0
0x2249da  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_odpContext
0x2249df  ldloc.0
0x2249e0  newobj   instance void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.CommonRowCache::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalabilityCache scaleCache)
0x2249e5  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::set_TablixProcessingLookupRowCache(class Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.CommonRowCache value)
0x2249ea  ldarg.0
0x2249eb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_dataSet
0x2249f0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo> Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_LookupDestinationInfos()
0x2249f5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo>::get_Count()
0x2249fa  stloc.1
0x2249fb  ldloc.1
0x2249fc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupObjResult>::.ctor(int32)
0x224a01  stloc.2
0x224a02  ldarg.0
0x224a03  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_dataSetInstance
0x224a08  ldloc.2
0x224a09  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::set_LookupResults(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupObjResult> value)
0x224a0e  ldc.i4.0
0x224a0f  stloc.3
0x224a10  br.s     loc_224A50
0x224a12  ldarg.0
0x224a13  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_dataSet
0x224a18  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo> Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_LookupDestinationInfos()
0x224a1d  ldloc.3
0x224a1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo>::get_Item(!!T0)
0x224a23  stloc.s  4
0x224a25  ldloc.0
0x224a26  ldarg.0
0x224a27  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeLookupProcessing::m_odpContext
0x224a2c  callvirt instance class Microsoft.ReportingServices.Common.IDataComparer Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ProcessingComparer()
0x224a31  ldloc.s  4
0x224a33  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.LookupDestinationInfo::get_UsedInSameDataSetTablixProcessing()
0x224a38  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.LookupTable::.ctor(class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IScalabilityCache scalabilityCache, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<object> comparer, bool mustStoreDataRows)
0x224a3d  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.LookupObjResult::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.LookupTable lookupTable)
0x224a42  stloc.s  5
0x224a44  ldloc.2
0x224a45  ldloc.s  5
0x224a47  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupObjResult>::Add(var<u1>)
0x224a4c  ldloc.3
0x224a4d  ldc.i4.1
0x224a4e  add
0x224a4f  stloc.3
0x224a50  ldloc.3
0x224a51  ldloc.1
0x224a52  blt.s    loc_224A12
0x224a54  ret
```
