# Microsoft.SharePoint.Taxonomy.TermCollection::MoveNext

- ea: `0x51880`
- end: `0x5198a`
- name: `Microsoft.SharePoint.Taxonomy.TermCollection::MoveNext`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x51850`

## callees

- `0x2f380`
- `0x4dd20`
- `0x51880`
- `0x56bd0`

## string_xrefs

- `0x5188c`: `Begin: TermCollection.MoveNext()`
- `0x5197e`: `End: TermCollection.MoveNext()`

## pseudocode

```c

```

## disassembly

```asm
0x51880  ldc.i4   0x32657762
0x51885  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5188a  ldc.i4.s 0x64
0x5188c  ldstr    aBeginTermcolle// "Begin: TermCollection.MoveNext()"
0x51891  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51896  ldarg.0
0x51897  ldfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingLimit
0x5189c  brtrue.s loc_518A0
0x5189e  ldc.i4.0
0x5189f  ret
0x518a0  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::.ctor()
0x518a5  stloc.0
0x518a6  ldc.i4.0
0x518a7  stloc.1
0x518a8  br.s     loc_518D3
0x518aa  ldloc.0
0x518ab  ldarg.0
0x518ac  ldfld    class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.TermCollection::allItemIds
0x518b1  ldarg.0
0x518b2  ldfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingIndex
0x518b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x518bc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x518c1  ldloc.1
0x518c2  ldc.i4.1
0x518c3  add.ovf
0x518c4  stloc.1
0x518c5  ldarg.0
0x518c6  dup
0x518c7  ldfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingIndex
0x518cc  ldc.i4.1
0x518cd  add.ovf
0x518ce  stfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingIndex
0x518d3  ldloc.1
0x518d4  ldarg.0
0x518d5  ldfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingLimit
0x518da  bge.s    loc_518EF
0x518dc  ldarg.0
0x518dd  ldfld    int32 Microsoft.SharePoint.Taxonomy.TermCollection::pagingIndex
0x518e2  ldarg.0
0x518e3  ldfld    class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.TermCollection::allItemIds
0x518e8  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x518ed  blt.s    loc_518AA
0x518ef  ldc.i4.0
0x518f0  stloc.2
0x518f1  ldloc.0
0x518f2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x518f7  ldc.i4.0
0x518f8  ble.s    loc_51970
0x518fa  ldc.i4.1
0x518fb  stloc.2
0x518fc  ldarg.0
0x518fd  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TermCollection::pagingTermStore
0x51902  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x51907  ldloc.0
0x51908  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTerms(class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid> termGuids)
0x5190d  stloc.3
0x5190e  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Taxonomy.Term>::.ctor()
0x51913  stloc.s  4
0x51915  ldloc.3
0x51916  brfalse.s loc_51966
0x51918  ldloc.3
0x51919  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::GetEnumerator()
0x5191e  stloc.s  7
0x51920  br.s     loc_5194D
0x51922  ldloca.s 7
0x51924  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::get_Current()
0x51929  stloc.s  5
0x5192b  ldloc.s  5
0x5192d  ldarg.0
0x5192e  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermCollection::pagingTermSet
0x51933  ldarg.0
0x51934  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TermCollection::pagingTermStore
0x51939  call     class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::TryCreateTerm(class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm sharedTerm, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet sharedTermSet, class Microsoft.SharePoint.Taxonomy.TermStore termStore)
0x5193e  stloc.s  6
0x51940  ldloc.s  6
0x51942  brfalse.s loc_5194D
0x51944  ldloc.s  4
0x51946  ldloc.s  6
0x51948  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Taxonomy.Term>::Add(var<u1>)
0x5194d  ldloca.s 7
0x5194f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>::MoveNext()
0x51954  brtrue.s loc_51922
0x51956  leave.s  loc_51966
0x51958  ldloca.s 7
0x5195a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm>
0x51960  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51965  endfinally
0x51966  ldarg.0
0x51967  ldloc.s  4
0x51969  call     instance void class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::UpdatePagedCollection(class [mscorlib]System.Collections.ObjectModel.Collection`1<var<u1>>)
0x5196e  br.s     loc_51972
0x51970  ldc.i4.0
0x51971  stloc.2
0x51972  ldc.i4   0x32657763
0x51977  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5197c  ldc.i4.s 0x64
0x5197e  ldstr    aEndTermcollect// "End: TermCollection.MoveNext()"
0x51983  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x51988  ldloc.2
0x51989  ret
```
