# Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::.cctor

- ea: `0x23940`
- end: `0x23a45`
- name: `Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::.cctor`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x23940`

## string_xrefs

- `0x239b6`: `TaxonomyCacheHelpers initialized with UsingForegroundFlushing={0} based on SPServer key`
- `0x239f2`: `TaxonomyCacheHelpers initialized with UsingForegroundFlushing={0} based on flight`
- `0x23a23`: `TaxonomyCacheHelpers failed to query UsingForegroundFlushing: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x23940  newobj   instance void [mscorlib]System.Threading.ReaderWriterLock::.ctor()
0x23945  stsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::taxonomyCacheLock
0x2394a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache>::.ctor()
0x2394f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache> Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::caches
0x23954  newobj   instance void [mscorlib]System.Threading.ReaderWriterLock::.ctor()
0x23959  stsfld   class [mscorlib]System.Threading.ReaderWriterLock Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::threadInitializationLock
0x2395e  ldc.i4   0x3E8
0x23963  stsfld   int32 Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::checkForChangesInterval
0x23968  ldloca.s 0
0x2396a  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x23970  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServer::get_Local()
0x23975  stloc.1
0x23976  ldloc.1
0x23977  ldnull
0x23978  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x2397d  brfalse.s loc_23995
0x2397f  ldloc.1
0x23980  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x23985  ldstr    aTaxonomymindbf// "TaxonomyMinDbForegroundFlushing"
0x2398a  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2398f  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x23994  stloc.0
0x23995  ldloca.s 0
0x23997  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2399c  brfalse.s loc_239D7
0x2399e  ldloca.s 0
0x239a0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x239a5  stsfld   bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::usingForegroundFlushing
0x239aa  ldc.i4   0x78C88B
0x239af  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x239b4  ldc.i4.s 0x14
0x239b6  ldstr    aTaxonomycacheh// "TaxonomyCacheHelpers initialized with U"...
0x239bb  ldc.i4.1
0x239bc  newarr   [mscorlib]System.Object
0x239c1  stloc.3
0x239c2  ldloc.3
0x239c3  ldc.i4.0
0x239c4  ldsfld   bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::usingForegroundFlushing
0x239c9  box      [mscorlib]System.Boolean
0x239ce  stelem.ref
0x239cf  ldloc.3
0x239d0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x239d5  br.s     loc_23A14
0x239d7  ldc.i4   0x2A15
0x239dc  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x239e1  stsfld   bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::usingForegroundFlushing
0x239e6  ldc.i4   0x78C88C
0x239eb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x239f0  ldc.i4.s 0x14
0x239f2  ldstr    aTaxonomycacheh_0// "TaxonomyCacheHelpers initialized with U"...
0x239f7  ldc.i4.1
0x239f8  newarr   [mscorlib]System.Object
0x239fd  stloc.s  4
0x239ff  ldloc.s  4
0x23a01  ldc.i4.0
0x23a02  ldsfld   bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::usingForegroundFlushing
0x23a07  box      [mscorlib]System.Boolean
0x23a0c  stelem.ref
0x23a0d  ldloc.s  4
0x23a0f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x23a14  leave.s  loc_23A44
0x23a16  stloc.2
0x23a17  ldc.i4   0x78C88D
0x23a1c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x23a21  ldc.i4.s 0xA
0x23a23  ldstr    aTaxonomycacheh_1// "TaxonomyCacheHelpers failed to query Us"...
0x23a28  ldc.i4.1
0x23a29  newarr   [mscorlib]System.Object
0x23a2e  stloc.s  5
0x23a30  ldloc.s  5
0x23a32  ldc.i4.0
0x23a33  ldloc.2
0x23a34  stelem.ref
0x23a35  ldloc.s  5
0x23a37  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x23a3c  ldc.i4.0
0x23a3d  stsfld   bool Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCacheHelpers::usingForegroundFlushing
0x23a42  leave.s  loc_23A44
0x23a44  ret
```
