# Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::GetCache

- ea: `0x23a50`
- end: `0x23b77`
- name: `Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::GetCache`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x56df0`

## callees

- `0x20590`
- `0x20d80`
- `0x23a50`
- `0x23cd0`
- `0x242a0`
- `0x56c60`

## string_xrefs

- `0x23ac5`: `Constructing a ForegroundFlushingTaxonomyCache for SharedServiceId={0}`
- `0x23afd`: `End of the construction of ForegroundFlushingTaxonomyCache.`
- `0x23b15`: `Constructing a BackgroundFlushingTaxonomyCache for SharedServiceId={0}`
- `0x23b4d`: `End of the construction of BackgroundFlushingTaxonomyCache.`

## pseudocode

```c

```

## disassembly

```asm
0x23a50  ldarg.0
0x23a51  ldstr    aTermstore_0// "termStore"
0x23a56  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x23a5b  ldsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::taxonomyCacheLock
0x23a60  ldc.i4.m1
0x23a61  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireReaderLock(int32)
0x23a66  ldnull
0x23a67  stloc.0
0x23a68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache> Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::caches
0x23a6d  ldarg.0
0x23a6e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23a73  ldloca.s 0
0x23a75  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache>::TryGetValue(var<u1>, !!T0)
0x23a7a  pop
0x23a7b  leave.s  loc_23A88
0x23a7d  ldsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::taxonomyCacheLock
0x23a82  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseReaderLock()
0x23a87  endfinally
0x23a88  ldloc.0
0x23a89  brtrue   loc_23B75
0x23a8e  ldsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::taxonomyCacheLock
0x23a93  ldc.i4.m1
0x23a94  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::AcquireWriterLock(int32)
0x23a99  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache> Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::caches
0x23a9e  ldarg.0
0x23a9f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23aa4  ldloca.s 0
0x23aa6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache>::TryGetValue(var<u1>, !!T0)
0x23aab  pop
0x23aac  ldloc.0
0x23aad  brtrue   loc_23B68
0x23ab2  call     bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::get_UsingForegroundFlushing()
0x23ab7  brfalse.s loc_23B09
0x23ab9  ldc.i4   0x78C88E
0x23abe  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x23ac3  ldc.i4.s 0x14
0x23ac5  ldstr    aConstructingAF// "Constructing a ForegroundFlushingTaxono"...
0x23aca  ldc.i4.1
0x23acb  newarr   [mscorlib]System.Object
0x23ad0  stloc.1
0x23ad1  ldloc.1
0x23ad2  ldc.i4.0
0x23ad3  ldarg.0
0x23ad4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23ad9  box      [mscorlib]System.Guid
0x23ade  stelem.ref
0x23adf  ldloc.1
0x23ae0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x23ae5  ldarg.0
0x23ae6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23aeb  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.ForegroundFlushingTaxonomyCache::.ctor(valuetype [mscorlib]System.Guid sharedServiceId)
0x23af0  stloc.0
0x23af1  ldc.i4   0x78C88F
0x23af6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x23afb  ldc.i4.s 0x14
0x23afd  ldstr    aEndOfTheConstr// "End of the construction of ForegroundFl"...
0x23b02  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x23b07  br.s     loc_23B57
0x23b09  ldc.i4   0x31346679
0x23b0e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x23b13  ldc.i4.s 0x14
0x23b15  ldstr    aConstructingAB// "Constructing a BackgroundFlushingTaxono"...
0x23b1a  ldc.i4.1
0x23b1b  newarr   [mscorlib]System.Object
0x23b20  stloc.2
0x23b21  ldloc.2
0x23b22  ldc.i4.0
0x23b23  ldarg.0
0x23b24  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23b29  box      [mscorlib]System.Guid
0x23b2e  stelem.ref
0x23b2f  ldloc.2
0x23b30  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x23b35  ldarg.0
0x23b36  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23b3b  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.BackgroundFlushingTaxonomyCache::.ctor(valuetype [mscorlib]System.Guid sharedServiceId)
0x23b40  stloc.0
0x23b41  ldc.i4   0x3134667A
0x23b46  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x23b4b  ldc.i4.s 0x14
0x23b4d  ldstr    aEndOfTheConstr_0// "End of the construction of BackgroundFl"...
0x23b52  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x23b57  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache> Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::caches
0x23b5c  ldarg.0
0x23b5d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceId()
0x23b62  ldloc.0
0x23b63  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache>::set_Item(var<u1>, !!T0)
0x23b68  leave.s  loc_23B75
0x23b6a  ldsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::taxonomyCacheLock
0x23b6f  callvirt instance void [mscorlib]System.Threading.ReaderWriterLock::ReleaseWriterLock()
0x23b74  endfinally
0x23b75  ldloc.0
0x23b76  ret
```
