# Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet::RunEmbeddedQuery

- ea: `0x1f5f30`
- end: `0x1f5f60`
- name: `Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet::RunEmbeddedQuery`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1f5b20`

## callees

- `0x1f5fa0`
- `0x1f7c20`
- `0x1fb370`
- `0x1fd350`

## string_xrefs

- `0x1f5f48`: `When query execution caching is enabled, new queries must not be run outside query prefetch.`

## pseudocode

```c

```

## disassembly

```asm
0x1f5f30  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1f5f35  ldarg.0
0x1f5f36  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::m_odpContext
0x1f5f3b  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_StateManager()
0x1f5f40  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.ExecutedQueryCache Microsoft.ReportingServices.OnDemandProcessing.OnDemandStateManager::get_ExecutedQueryCache()
0x1f5f45  ldnull
0x1f5f46  ceq
0x1f5f48  ldstr    aWhenQueryExecu// "When query execution caching is enabled"...
0x1f5f4d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1f5f52  ldarg.0
0x1f5f53  ldarg.1
0x1f5f54  ldarg.2
0x1f5f55  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader Microsoft.ReportingServices.OnDemandProcessing.RuntimeLiveQueryExecutor::RunLiveQuery(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> queryParams, object[] paramValues)
0x1f5f5a  call     bool Microsoft.ReportingServices.OnDemandProcessing.RuntimeDataSet::ReaderExtensionsSupported(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader reader)
0x1f5f5f  ret
```
