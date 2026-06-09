# Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogListItems

- ea: `0x44290`
- end: `0x444a5`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogListItems`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x47a50`
- `0x55d60`

## callees

- `0x43790`
- `0x43fb0`
- `0x441a0`
- `0x44290`

## string_xrefs

- `0x443d9`: `Exception iterating over lists in UpdateCatalogListItems.`
- `0x4441e`: `Exception iterating over lists / webs in UpdateCatalogListItems.`
- `0x4446d`: `Can't find taxonomy hidden list in site {0} in UpdateCatalogListItems.`
- `0x4449a`: `Catalog feature not enabled on site collection, skipping catalog update.`

## pseudocode

```c

```

## disassembly

```asm
0x44290  ldc.i4   0x158563
0x44295  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4429a  ldc.i4.s 0x64
0x4429c  ldstr    aUpdatingCatalo// "Updating Catalog List Items."
0x442a1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x442a6  ldarg.0
0x442a7  brfalse  loc_444A4
0x442ac  ldarg.1
0x442ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x442b2  ldc.i4.0
0x442b3  ble      loc_444A4
0x442b8  ldarg.0
0x442b9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Features()
0x442be  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::catalogPublishingFeatureId
0x442c3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::get_Item(valuetype [mscorlib]System.Guid)
0x442c8  brfalse  loc_4448B
0x442cd  ldnull
0x442ce  stloc.0
0x442cf  ldarg.0
0x442d0  ldloca.s 0
0x442d2  call     bool Microsoft.SharePoint.Taxonomy.TaxonomyField::TryGetHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.SPList& list)
0x442d7  brfalse  loc_44461
0x442dc  ldc.i4   0x158580
0x442e1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x442e6  ldc.i4   0xC8
0x442eb  ldstr    aIteratingOverE// "Iterating over each web in site for cat"...
0x442f0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x442f5  ldarg.0
0x442f6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWebCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_AllWebs()
0x442fb  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x44300  stloc.s  5
0x44302  br       loc_4443E
0x44307  ldloc.s  5
0x44309  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4430e  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x44313  stloc.1
0x44314  ldloc.1
0x44315  stloc.s  6
0x44317  ldc.i4   0x158581
0x4431c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x44321  ldc.i4   0xC8
0x44326  ldstr    aIteratingOverE_0// "Iterating over each list in web to find"...
0x4432b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x44330  ldloc.1
0x44331  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Lists()
0x44336  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x4433b  stloc.s  7
0x4433d  br       loc_443EB
0x44342  ldloc.s  7
0x44344  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x44349  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPList
0x4434e  stloc.2
0x4434f  ldloc.2
0x44350  call     bool Microsoft.SharePoint.Taxonomy.TaxonomyField::IsListPublishingCatalog(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList spList)
0x44355  brfalse.s loc_44394
0x44357  ldc.i4   0x158582
0x4435c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x44361  ldc.i4.s 0x32
0x44363  ldstr    aPushingTaxonom// "Pushing taxonomy hierachy changes into "...
0x44368  ldc.i4.2
0x44369  newarr   [mscorlib]System.Object
0x4436e  stloc.s  8
0x44370  ldloc.s  8
0x44372  ldc.i4.0
0x44373  ldloc.2
0x44374  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0x44379  stelem.ref
0x4437a  ldloc.s  8
0x4437c  ldc.i4.1
0x4437d  ldloc.1
0x4437e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x44383  stelem.ref
0x44384  ldloc.s  8
0x44386  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4438b  ldloc.2
0x4438c  ldarg.1
0x4438d  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, class [mscorlib]System.Collections.Generic.List`1<int32> listItemIdsForCatalogPush)
0x44392  br.s     loc_443CB
0x44394  ldc.i4   0x158583
0x44399  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4439e  ldc.i4   0xC8
0x443a3  ldstr    aList0InWeb1IsN// "List {0} in web {1} is not a catalog."
0x443a8  ldc.i4.2
0x443a9  newarr   [mscorlib]System.Object
0x443ae  stloc.s  9
0x443b0  ldloc.s  9
0x443b2  ldc.i4.0
0x443b3  ldloc.2
0x443b4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0x443b9  stelem.ref
0x443ba  ldloc.s  9
0x443bc  ldc.i4.1
0x443bd  ldloc.1
0x443be  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x443c3  stelem.ref
0x443c4  ldloc.s  9
0x443c6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x443cb  leave.s  loc_443EB
0x443cd  stloc.3
0x443ce  ldc.i4   0x158584
0x443d3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x443d8  ldloc.3
0x443d9  ldstr    aExceptionItera// "Exception iterating over lists in Updat"...
0x443de  ldc.i4.0
0x443df  newarr   [mscorlib]System.Object
0x443e4  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x443e9  leave.s  loc_443EB
0x443eb  ldloc.s  7
0x443ed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x443f2  brtrue   loc_44342
0x443f7  leave.s  loc_4440E
0x443f9  ldloc.s  7
0x443fb  isinst   [mscorlib]System.IDisposable
0x44400  stloc.s  0xA
0x44402  ldloc.s  0xA
0x44404  brfalse.s loc_4440D
0x44406  ldloc.s  0xA
0x44408  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4440d  endfinally
0x4440e  leave.s  loc_44430
0x44410  stloc.s  4
0x44412  ldc.i4   0x158585
0x44417  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4441c  ldloc.s  4
0x4441e  ldstr    aExceptionItera_0// "Exception iterating over lists / webs i"...
0x44423  ldc.i4.0
0x44424  newarr   [mscorlib]System.Object
0x44429  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x4442e  leave.s  loc_44430
0x44430  leave.s  loc_4443E
0x44432  ldloc.s  6
0x44434  brfalse.s loc_4443D
0x44436  ldloc.s  6
0x44438  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4443d  endfinally
0x4443e  ldloc.s  5
0x44440  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x44445  brtrue   loc_44307
0x4444a  leave.s  loc_4448B
0x4444c  ldloc.s  5
0x4444e  isinst   [mscorlib]System.IDisposable
0x44453  stloc.s  0xB
0x44455  ldloc.s  0xB
0x44457  brfalse.s loc_44460
0x44459  ldloc.s  0xB
0x4445b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x44460  endfinally
0x44461  ldc.i4   0x158586
0x44466  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4446b  ldc.i4.s 0xA
0x4446d  ldstr    aCanTFindTaxono// "Can't find taxonomy hidden list in site"...
0x44472  ldc.i4.1
0x44473  newarr   [mscorlib]System.Object
0x44478  stloc.s  0xC
0x4447a  ldloc.s  0xC
0x4447c  ldc.i4.0
0x4447d  ldarg.0
0x4447e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x44483  stelem.ref
0x44484  ldloc.s  0xC
0x44486  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4448b  ldc.i4   0x158587
0x44490  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x44495  ldc.i4   0xC8
0x4449a  ldstr    aCatalogFeature// "Catalog feature not enabled on site col"...
0x4449f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x444a4  ret
```
