# Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogList

- ea: `0x441a0`
- end: `0x44284`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogList`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x44290`

## callees

- `0x43ff0`
- `0x441a0`

## string_xrefs

- `0x441c3`: `Couldn't find taxonomy catch all column in list {0} in web {1}.  Skipping catalog update`
- `0x44226`: `Batching catalog updates.`
- `0x44267`: `Processing remaining catalog updates.`

## pseudocode

```c

```

## disassembly

```asm
0x441a0  ldarg.0
0x441a1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Fields()
0x441a6  ldstr    aF3b0adf9C1a24b// "{F3B0ADF9-C1A2-4b02-920D-943FBA4B3611}"
0x441ab  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x441b0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection::Contains(valuetype [mscorlib]System.Guid)
0x441b5  brtrue.s loc_441E8
0x441b7  ldc.i4   0x158560
0x441bc  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x441c1  ldc.i4.s 0x32
0x441c3  ldstr    aCouldnTFindTax// "Couldn't find taxonomy catch all column"...
0x441c8  ldc.i4.2
0x441c9  newarr   [mscorlib]System.Object
0x441ce  stloc.3
0x441cf  ldloc.3
0x441d0  ldc.i4.0
0x441d1  ldarg.0
0x441d2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Title()
0x441d7  stelem.ref
0x441d8  ldloc.3
0x441d9  ldc.i4.1
0x441da  ldarg.0
0x441db  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_ParentWebUrl()
0x441e0  stelem.ref
0x441e1  ldloc.3
0x441e2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x441e7  ret
0x441e8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::.ctor()
0x441ed  stloc.0
0x441ee  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x441f3  stloc.1
0x441f4  ldarg.1
0x441f5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x441fa  stloc.s  4
0x441fc  br.s     loc_4423F
0x441fe  ldloca.s 4
0x44200  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x44205  stloc.2
0x44206  ldloc.1
0x44207  ldloc.2
0x44208  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x4420d  ldloc.1
0x4420e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x44213  ldc.i4.s 0x32
0x44215  ble.s    loc_4423F
0x44217  ldc.i4   0x158561
0x4421c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x44221  ldc.i4   0xC8
0x44226  ldstr    aBatchingCatalo// "Batching catalog updates."
0x4422b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x44230  ldarg.0
0x44231  ldloc.1
0x44232  ldloca.s 0
0x44234  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::ProcessCatalogList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, class [mscorlib]System.Collections.Generic.List`1<int32> currentBatchOfIds, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>& alreadyUpdatedItems)
0x44239  ldloc.1
0x4423a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Clear()
0x4423f  ldloca.s 4
0x44241  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x44246  brtrue.s loc_441FE
0x44248  leave.s  loc_44258
0x4424a  ldloca.s 4
0x4424c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x44252  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x44257  endfinally
0x44258  ldc.i4   0x158562
0x4425d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x44262  ldc.i4   0xC8
0x44267  ldstr    aProcessingRema// "Processing remaining catalog updates."
0x4426c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x44271  ldloc.1
0x44272  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x44277  ldc.i4.0
0x44278  ble.s    loc_44283
0x4427a  ldarg.0
0x4427b  ldloc.1
0x4427c  ldloca.s 0
0x4427e  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::ProcessCatalogList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPList list, class [mscorlib]System.Collections.Generic.List`1<int32> currentBatchOfIds, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>& alreadyUpdatedItems)
0x44283  ret
```
