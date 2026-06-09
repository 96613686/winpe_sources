# Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheStatistics::GetCountersFromContext

- ea: `0x23f70`
- end: `0x23ffa`
- name: `Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheStatistics::GetCountersFromContext`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x23db0`
- `0x23eb0`

## callees

- `0x23f70`
- `0x24020`

## string_xrefs

- `0x23f91`: `taxonomy_cache_counters`
- `0x23fcd`: `taxonomy_cache_counters`
- `0x23fea`: `taxonomy_cache_counters`

## pseudocode

```c

```

## disassembly

```asm
0x23f70  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x23f75  stloc.0
0x23f76  ldloc.0
0x23f77  brtrue.s loc_23F7B
0x23f79  ldnull
0x23f7a  ret
0x23f7b  ldc.i4.0
0x23f7c  stloc.2
0x23f7d  ldsfld   object Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheStatistics::initializationLock
0x23f82  dup
0x23f83  stloc.3
0x23f84  ldloca.s 2
0x23f86  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x23f8b  ldloc.0
0x23f8c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x23f91  ldstr    aTaxonomyCacheC// "taxonomy_cache_counters"
0x23f96  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x23f9b  brtrue.s loc_23FD8
0x23f9d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters>::.ctor()
0x23fa2  stloc.1
0x23fa3  ldloc.1
0x23fa4  ldc.i4.2
0x23fa5  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters::.ctor()
0x23faa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters>::set_Item(var<u1>, !!T0)
0x23faf  ldloc.1
0x23fb0  ldc.i4.1
0x23fb1  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters::.ctor()
0x23fb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters>::set_Item(var<u1>, !!T0)
0x23fbb  ldloc.1
0x23fbc  ldc.i4.0
0x23fbd  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters::.ctor()
0x23fc2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters>::set_Item(var<u1>, !!T0)
0x23fc7  ldloc.0
0x23fc8  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x23fcd  ldstr    aTaxonomyCacheC// "taxonomy_cache_counters"
0x23fd2  ldloc.1
0x23fd3  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x23fd8  leave.s  loc_23FE4
0x23fda  ldloc.2
0x23fdb  brfalse.s loc_23FE3
0x23fdd  ldloc.3
0x23fde  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x23fe3  endfinally
0x23fe4  ldloc.0
0x23fe5  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x23fea  ldstr    aTaxonomyCacheC// "taxonomy_cache_counters"
0x23fef  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x23ff4  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheCounters>
0x23ff9  ret
```
