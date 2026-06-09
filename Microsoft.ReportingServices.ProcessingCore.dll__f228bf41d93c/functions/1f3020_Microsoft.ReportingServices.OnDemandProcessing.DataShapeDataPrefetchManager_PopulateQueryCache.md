# Microsoft.ReportingServices.OnDemandProcessing.DataShapeDataPrefetchManager::PopulateQueryCache

- ea: `0x1f3020`
- end: `0x1f3093`
- name: `Microsoft.ReportingServices.OnDemandProcessing.DataShapeDataPrefetchManager::PopulateQueryCache`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1f2ea0`

## callees

- `0x1f3020`
- `0x1f33e0`
- `0x1f34a0`
- `0x1f8960`
- `0x1fb370`
- `0x1fd360`

## string_xrefs

- `0x1f303a`: `ExecutedQueryCache should have been setup`

## pseudocode

```c

```

## disassembly

```asm
0x1f3020  ldarg.0
0x1f3021  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.DataShapeDataPrefetchManager::m_odpContext
0x1f3026  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_StateManager()
0x1f302b  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.ExecutedQueryCache Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::SetupExecutedQueryCache()
0x1f3030  stloc.0
0x1f3031  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f3036  ldloc.0
0x1f3037  ldnull
0x1f3038  cgt.un
0x1f303a  ldstr    aExecutedqueryc// "ExecutedQueryCache should have been set"...
0x1f303f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1f3044  ldarg.0
0x1f3045  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor> Microsoft.ReportingServices.OnDemandProcessing.DataShapeDataPrefetchManager::m_queryExecutors
0x1f304a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor>::GetEnumerator()
0x1f304f  stloc.1
0x1f3050  br.s     loc_1F3079
0x1f3052  ldloca.s 1
0x1f3054  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor>::get_Current()
0x1f3059  stloc.2
0x1f305a  ldnull
0x1f305b  stloc.3
0x1f305c  ldloc.2
0x1f305d  ldloca.s 3
0x1f305f  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor::CreateQuery([out] class Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery& query)
0x1f3064  ldloc.0
0x1f3065  ldloc.3
0x1f3066  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.ExecutedQueryCache::Add(class Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery query)
0x1f306b  leave.s  loc_1F3079
0x1f306d  pop
0x1f306e  ldloc.3
0x1f306f  brfalse.s loc_1F3077
0x1f3071  ldloc.3
0x1f3072  callvirt instance void Microsoft.ReportingServices.OnDemandProcessing.ExecutedQuery::Close()
0x1f3077  rethrow
0x1f3079  ldloca.s 1
0x1f307b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor>::MoveNext()
0x1f3080  brtrue.s loc_1F3052
0x1f3082  leave.s  loc_1F3092
0x1f3084  ldloca.s 1
0x1f3086  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.OnDemandProcessing.RuntimeQueryExecutor>
0x1f308c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f3091  endfinally
0x1f3092  ret
```
