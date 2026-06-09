# Microsoft.ReportingServices.Library.RSLocalCacheManager::GetCachedResult

- ea: `0x5b880`
- end: `0x5b905`
- name: `Microsoft.ReportingServices.Library.RSLocalCacheManager::GetCachedResult`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b370`
- `0x2c540`

## callees

- `0x5a4f0`
- `0x5b0b0`
- `0x5b0f0`
- `0x5b610`
- `0x5b880`

## string_xrefs

- `0x5b8c4`: `Found key in cache: `
- `0x5b8ed`: `Key not found in cache: `

## pseudocode

```c

```

## disassembly

```asm
0x5b880  ldnull
0x5b881  stloc.0
0x5b882  ldarg.2
0x5b883  brtrue.s loc_5B88F
0x5b885  ldarg.1
0x5b886  ldarg.3
0x5b887  call     string Microsoft.ReportingServices.Library.CompositeCacheBuilder::BuildMainStreamKey(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext context, class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot)
0x5b88c  stloc.0
0x5b88d  br.s     loc_5B898
0x5b88f  ldarg.1
0x5b890  ldarg.2
0x5b891  ldarg.3
0x5b892  call     string Microsoft.ReportingServices.Library.CompositeCacheBuilder::BuildSecondaryStreamKey(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext context, string streamName, class Microsoft.ReportingServices.Library.ReportSnapshot reportSnapshot)
0x5b897  stloc.0
0x5b898  ldloc.0
0x5b899  brtrue.s loc_5B89D
0x5b89b  ldnull
0x5b89c  ret
0x5b89d  ldarg.0
0x5b89e  ldfld    class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.RSLocalCacheManager::cache
0x5b8a3  ldloc.0
0x5b8a4  callvirt instance object [System.Web]System.Web.Caching.Cache::get_Item(string)
0x5b8a9  castclass Microsoft.ReportingServices.Library.CachedRenderingResult
0x5b8ae  stloc.1
0x5b8af  ldloc.1
0x5b8b0  brfalse.s loc_5B8DB
0x5b8b2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b8b7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5b8bc  brfalse.s loc_5B8D4
0x5b8be  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b8c3  ldc.i4.4
0x5b8c4  ldstr    aFoundKeyInCach// "Found key in cache: "
0x5b8c9  ldloc.0
0x5b8ca  call     string [mscorlib]System.String::Concat(string, string)
0x5b8cf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5b8d4  ldloc.1
0x5b8d5  callvirt instance class Microsoft.ReportingServices.Library.ReportRenderingResult Microsoft.ReportingServices.Library.CachedRenderingResult::GetRenderingResult()
0x5b8da  ret
0x5b8db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b8e0  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5b8e5  brfalse.s loc_5B8FD
0x5b8e7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b8ec  ldc.i4.4
0x5b8ed  ldstr    aKeyNotFoundInC// "Key not found in cache: "
0x5b8f2  ldloc.0
0x5b8f3  call     string [mscorlib]System.String::Concat(string, string)
0x5b8f8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5b8fd  ldarg.0
0x5b8fe  call     instance void Microsoft.ReportingServices.Library.RSLocalCacheManager::PrintCachedItems()
0x5b903  ldnull
0x5b904  ret
```
