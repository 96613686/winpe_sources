# Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsCurrentBatchSuccess

- ea: `0x59240`
- end: `0x596bf`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsCurrentBatchSuccess`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x59bf0`

## callees

- `0x48810`
- `0x4f560`
- `0x58520`
- `0x58530`
- `0x58540`
- `0x58550`
- `0x58560`
- `0x58570`
- `0x58580`
- `0x58590`
- `0x59240`

## string_xrefs

- `0x59550`: `Not all Groups were created!`
- `0x59586`: `Not all Term Sets were created!`
- `0x595bc`: `Not all memberships were created!`
- `0x595f2`: `Not all sources Terms were created!`
- `0x5961f`: `Not all pinned Terms were created!`
- `0x5965d`: `Not all source term memberships were created!`

## pseudocode

```c

```

## disassembly

```asm
0x59240  ldc.i4   0x121058D
0x59245  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5924a  ldc.i4.s 0x32
0x5924c  ldstr    aBeginRefreshed// "Begin refreshed current batch"
0x59251  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x59256  ldarg.0
0x59257  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x5925c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_Groups()
0x59261  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group>::GetEnumerator()
0x59266  stloc.s  9
0x59268  br.s     loc_59294
0x5926a  ldloc.s  9
0x5926c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Group>::get_Current()
0x59271  stloc.0
0x59272  ldarg.0
0x59273  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreGroups
0x59278  ldloc.0
0x59279  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5927e  ldarg.0
0x5927f  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::termStore
0x59284  ldloc.0
0x59285  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5928a  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid)
0x5928f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermGroup>::set_Item(var<u1>, !!T0)
0x59294  ldloc.s  9
0x59296  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5929b  brtrue.s loc_5926A
0x5929d  leave.s  loc_592AB
0x5929f  ldloc.s  9
0x592a1  brfalse.s loc_592AA
0x592a3  ldloc.s  9
0x592a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x592aa  endfinally
0x592ab  ldarg.0
0x592ac  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x592b1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermSets()
0x592b6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet>::GetEnumerator()
0x592bb  stloc.s  0xA
0x592bd  br.s     loc_592E9
0x592bf  ldloc.s  0xA
0x592c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.TermSet>::get_Current()
0x592c6  stloc.1
0x592c7  ldarg.0
0x592c8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTermSets
0x592cd  ldloc.1
0x592ce  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x592d3  ldarg.0
0x592d4  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::termStore
0x592d9  ldloc.1
0x592da  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x592df  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid)
0x592e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermSet>::set_Item(var<u1>, !!T0)
0x592e9  ldloc.s  0xA
0x592eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x592f0  brtrue.s loc_592BF
0x592f2  leave.s  loc_59300
0x592f4  ldloc.s  0xA
0x592f6  brfalse.s loc_592FF
0x592f8  ldloc.s  0xA
0x592fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x592ff  endfinally
0x59300  ldarg.0
0x59301  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59306  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermMemberships()
0x5930b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x59310  stloc.s  0xB
0x59312  br.s     loc_59359
0x59314  ldloc.s  0xB
0x59316  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x5931b  stloc.2
0x5931c  ldarg.0
0x5931d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTermMemeberships
0x59322  ldloc.2
0x59323  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x59328  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5932d  ldloc.2
0x5932e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59333  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0)
0x59338  ldarg.0
0x59339  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::termStore
0x5933e  ldloc.2
0x5933f  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x59344  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59349  ldloc.2
0x5934a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5934f  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::GetTermInTermSet(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59354  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::set_Item(var<u1>, !!T0)
0x59359  ldloc.s  0xB
0x5935b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59360  brtrue.s loc_59314
0x59362  leave.s  loc_59370
0x59364  ldloc.s  0xB
0x59366  brfalse.s loc_5936F
0x59368  ldloc.s  0xB
0x5936a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5936f  endfinally
0x59370  ldarg.0
0x59371  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59376  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_SourceTerms()
0x5937b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x59380  stloc.s  0xC
0x59382  br.s     loc_593BE
0x59384  ldloc.s  0xC
0x59386  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x5938b  stloc.3
0x5938c  ldarg.0
0x5938d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTerms
0x59392  ldloc.3
0x59393  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59398  ldarg.0
0x59399  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::remoteTermStoreTermMemeberships
0x5939e  ldloc.3
0x5939f  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x593a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x593a9  ldloc.3
0x593aa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x593af  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0)
0x593b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::get_Item(void)
0x593b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::set_Item(var<u1>, !!T0)
0x593be  ldloc.s  0xC
0x593c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x593c5  brtrue.s loc_59384
0x593c7  leave.s  loc_593D5
0x593c9  ldloc.s  0xC
0x593cb  brfalse.s loc_593D4
0x593cd  ldloc.s  0xC
0x593cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x593d4  endfinally
0x593d5  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::.ctor()
0x593da  stloc.s  4
0x593dc  ldarg.0
0x593dd  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x593e2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_PinnedRootTerms()
0x593e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x593ec  stloc.s  0xD
0x593ee  br.s     loc_5941E
0x593f0  ldloc.s  0xD
0x593f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x593f7  stloc.s  5
0x593f9  ldloc.s  4
0x593fb  ldarg.0
0x593fc  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::termStore
0x59401  ldloc.s  5
0x59403  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x59408  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5940d  ldloc.s  5
0x5940f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x59414  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::GetTermInTermSet(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59419  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::Add(var<u1>)
0x5941e  ldloc.s  0xD
0x59420  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x59425  brtrue.s loc_593F0
0x59427  leave.s  loc_59435
0x59429  ldloc.s  0xD
0x5942b  brfalse.s loc_59434
0x5942d  ldloc.s  0xD
0x5942f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59434  endfinally
0x59435  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::.ctor()
0x5943a  stloc.s  6
0x5943c  ldarg.0
0x5943d  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59442  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_SourceTermMemberships()
0x59447  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::GetEnumerator()
0x5944c  stloc.s  0xE
0x5944e  br       loc_594EB
0x59453  ldloc.s  0xE
0x59455  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>>::get_Current()
0x5945a  stloc.s  7
0x5945c  ldarg.0
0x5945d  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::termStore
0x59462  ldloc.s  7
0x59464  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item1()
0x59469  ldloc.s  7
0x5946b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item2()
0x59470  callvirt instance class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore::GetTermInTermSet(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x59475  stloc.s  8
0x59477  ldloc.s  6
0x59479  ldloc.s  8
0x5947b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term>::Add(var<u1>)
0x59480  ldarg.0
0x59481  ldfld    class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.ClientContext Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::clientContext
0x59486  ldloc.s  8
0x59488  ldc.i4.1
0x59489  newarr   class [System.Core]System.Linq.Expressions.Expression`1<class [mscorlib]System.Func`2<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term, object>>
0x5948e  stloc.s  0xF
0x59490  ldloc.s  0xF
0x59492  ldc.i4.0
0x59493  ldtoken  [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term
0x59498  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5949d  ldstr    aTerm// "term"
0x594a2  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x594a7  stloc.s  0x10
0x594a9  ldloc.s  0x10
0x594ab  ldtoken  instance bool [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term::get_IsSourceTerm()
0x594b0  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x594b5  castclass [mscorlib]System.Reflection.MethodInfo
0x594ba  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x594bf  ldtoken  [mscorlib]System.Object
0x594c4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x594c9  call     class [System.Core]System.Linq.Expressions.UnaryExpression [System.Core]System.Linq.Expressions.Expression::ConvertChecked(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Type)
0x594ce  ldc.i4.1
0x594cf  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x594d4  stloc.s  0x11
0x594d6  ldloc.s  0x11
0x594d8  ldc.i4.0
0x594d9  ldloc.s  0x10
0x594db  stelem.ref
0x594dc  ldloc.s  0x11
0x594de  call     T0x2B00007A
0x594e3  stelem.ref
0x594e4  ldloc.s  0xF
0x594e6  callvirt T0x2B00007B
0x594eb  ldloc.s  0xE
0x594ed  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x594f2  brtrue   loc_59453
0x594f7  leave.s  loc_59505
0x594f9  ldloc.s  0xE
0x594fb  brfalse.s loc_59504
0x594fd  ldloc.s  0xE
0x594ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59504  endfinally
0x59505  ldarg.0
0x59506  ldfld    class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.ClientContext Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::clientContext
0x5950b  callvirt instance void [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext::ExecuteQuery()
0x59510  ldc.i4   0x121058E
0x59515  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5951a  ldc.i4.s 0x32
0x5951c  ldstr    aRefreshedCurre// "Refreshed current batch successfully"
0x59521  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x59526  ldarg.0
0x59527  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x5952c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Group> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_Groups()
0x59531  ldarg.0
0x59532  ldftn    instance bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::<IsCurrentBatchSuccess>b__0(class Microsoft.SharePoint.Taxonomy.Group group)
0x59538  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Group, bool>::.ctor(object, native int)
0x5953d  call     T0x2B00007C
0x59542  brfalse.s loc_5955C
0x59544  ldc.i4   0x121058F
0x59549  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5954e  ldc.i4.s 0x32
0x59550  ldstr    aNotAllGroupsWe// "Not all Groups were created!"
0x59555  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x5955a  ldc.i4.0
0x5955b  ret
0x5955c  ldarg.0
0x5955d  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59562  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.TermSet> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermSets()
0x59567  ldarg.0
0x59568  ldftn    instance bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::<IsCurrentBatchSuccess>b__1(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x5956e  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.TermSet, bool>::.ctor(object, native int)
0x59573  call     T0x2B00007D
0x59578  brfalse.s loc_59592
0x5957a  ldc.i4   0x1210590
0x5957f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59584  ldc.i4.s 0x32
0x59586  ldstr    aNotAllTermSets// "Not all Term Sets were created!"
0x5958b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x59590  ldc.i4.0
0x59591  ret
0x59592  ldarg.0
0x59593  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59598  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_TermMemberships()
0x5959d  ldarg.0
0x5959e  ldftn    instance bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::<IsCurrentBatchSuccess>b__2(class Microsoft.SharePoint.Taxonomy.Term membership)
0x595a4  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Term, bool>::.ctor(object, native int)
0x595a9  call     T0x2B00007E
0x595ae  brfalse.s loc_595C8
0x595b0  ldc.i4   0x1210591
0x595b5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x595ba  ldc.i4.s 0x32
0x595bc  ldstr    aNotAllMembersh// "Not all memberships were created!"
0x595c1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x595c6  ldc.i4.0
0x595c7  ret
0x595c8  ldarg.0
0x595c9  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x595ce  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::get_SourceTerms()
0x595d3  ldarg.0
0x595d4  ldftn    instance bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::<IsCurrentBatchSuccess>b__3(class Microsoft.SharePoint.Taxonomy.Term term)
0x595da  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Taxonomy.Term, bool>::.ctor(object, native int)
0x595df  call     T0x2B00007E
0x595e4  brfalse.s loc_595FE
0x595e6  ldc.i4   0x1210592
0x595eb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x595f0  ldc.i4.s 0x32
0x595f2  ldstr    aNotAllSourcesT// "Not all sources Terms were created!"
0x595f7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x595fc  ldc.i4.0
0x595fd  ret
0x595fe  ldloc.s  4
0x59600  ldnull
0x59601  ldftn    bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsClientObjectNull(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientObject clientObject)
0x59607  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.Term, bool>::.ctor(object, native int)
0x5960c  call     T0x2B00007F
0x59611  brfalse.s loc_5962B
0x59613  ldc.i4   0x1210593
0x59618  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5961d  ldc.i4.s 0x32
0x5961f  ldstr    aNotAllPinnedTe// "Not all pinned Terms were created!"
  ... truncated ...
```
