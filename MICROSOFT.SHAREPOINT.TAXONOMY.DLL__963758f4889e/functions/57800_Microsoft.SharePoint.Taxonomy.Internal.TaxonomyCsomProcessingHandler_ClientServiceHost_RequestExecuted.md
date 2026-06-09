# Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCsomProcessingHandler::ClientServiceHost_RequestExecuted

- ea: `0x57800`
- end: `0x578e3`
- name: `Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCsomProcessingHandler::ClientServiceHost_RequestExecuted`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x2ba10`
- `0x48ac0`
- `0x53f80`
- `0x55560`
- `0x56c30`
- `0x57800`

## string_xrefs

- `0x5780c`: `Begin: TaxonomyCsomProcessingHandler.ClientServiceHost_RequestExecuted`
- `0x578d8`: `End: TaxonomyCsomProcessingHandler.ClientServiceHost_RequestExecuted`

## pseudocode

```c

```

## disassembly

```asm
0x57800  ldc.i4   0x2181D3
0x57805  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5780a  ldc.i4.s 0x64
0x5780c  ldstr    aBeginTaxonomyc_2// "Begin: TaxonomyCsomProcessingHandler.Cl"...
0x57811  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x57816  ldarg.2
0x57817  ldstr    aE_0// "e"
0x5781c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57821  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::.ctor()
0x57826  stloc.0
0x57827  ldarg.2
0x57828  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientServiceEventArgs::get_RequestedObjects()
0x5782d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<object>::GetEnumerator()
0x57832  stloc.s  4
0x57834  br.s     loc_57872
0x57836  ldloc.s  4
0x57838  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<object>::get_Current()
0x5783d  stloc.1
0x5783e  ldloc.1
0x5783f  isinst   Microsoft.SharePoint.Taxonomy.TaxonomyItem
0x57844  stloc.2
0x57845  ldloc.2
0x57846  brfalse.s loc_57872
0x57848  ldloc.0
0x57849  ldloc.2
0x5784a  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x5784f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x57854  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::ContainsKey(var<u1>)
0x57859  brtrue.s loc_57872
0x5785b  ldloc.0
0x5785c  ldloc.2
0x5785d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x57862  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x57867  ldloc.2
0x57868  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x5786d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::Add(var<u1>, !!T0)
0x57872  ldloc.s  4
0x57874  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x57879  brtrue.s loc_57836
0x5787b  leave.s  loc_57889
0x5787d  ldloc.s  4
0x5787f  brfalse.s loc_57888
0x57881  ldloc.s  4
0x57883  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57888  endfinally
0x57889  ldloc.0
0x5788a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::get_Values()
0x5788f  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::GetEnumerator()
0x57894  stloc.s  5
0x57896  br.s     loc_578B3
0x57898  ldloca.s 5
0x5789a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::get_Current()
0x5789f  stloc.3
0x578a0  ldloc.3
0x578a1  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.Sandbox Microsoft.SharePoint.Taxonomy.TermStore::get_Sandbox()
0x578a6  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.Sandbox::get_HasAnyItems()
0x578ab  brfalse.s loc_578B3
0x578ad  ldloc.3
0x578ae  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x578b3  ldloca.s 5
0x578b5  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>::MoveNext()
0x578ba  brtrue.s loc_57898
0x578bc  leave.s  loc_578CC
0x578be  ldloca.s 5
0x578c0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.TermStore>
0x578c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x578cb  endfinally
0x578cc  ldc.i4   0x2181D4
0x578d1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x578d6  ldc.i4.s 0x64
0x578d8  ldstr    aEndTaxonomycso_0// "End: TaxonomyCsomProcessingHandler.Clie"...
0x578dd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x578e2  ret
```
