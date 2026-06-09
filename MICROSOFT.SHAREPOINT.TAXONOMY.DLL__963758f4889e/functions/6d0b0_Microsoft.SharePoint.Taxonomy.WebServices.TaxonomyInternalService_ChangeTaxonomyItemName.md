# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ChangeTaxonomyItemName

- ea: `0x6d0b0`
- end: `0x6d359`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ChangeTaxonomyItemName`
- size: `681`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x487f0`
- `0x48800`
- `0x4ba10`
- `0x4f3a0`
- `0x53f80`
- `0x545b0`
- `0x546d0`
- `0x54710`
- `0x55050`
- `0x55610`
- `0x6d0b0`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6df30`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6d0ce`: `TSMTWebServiceInvalidParam`
- `0x6d103`: `TSMTWebServiceInvalidParam`
- `0x6d1fd`: `TSMTWebServiceInvalidParam`
- `0x6d2e6`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6d0b0  ldarg.2
0x6d0b1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6d0b6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6d0bb  stloc.0
0x6d0bc  ldc.i4.0
0x6d0bd  stloc.1
0x6d0be  ldarg.1
0x6d0bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d0c4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d0c9  brfalse.s loc_6D0F2
0x6d0cb  ldc.i4.1
0x6d0cc  stloc.1
0x6d0cd  ldloc.0
0x6d0ce  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d0d3  ldc.i4.1
0x6d0d4  newarr   [mscorlib]System.Object
0x6d0d9  stloc.s  0xB
0x6d0db  ldloc.s  0xB
0x6d0dd  ldc.i4.0
0x6d0de  ldstr    aSspid// "sspId"
0x6d0e3  stelem.ref
0x6d0e4  ldloc.s  0xB
0x6d0e6  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d0eb  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d0f0  br.s     loc_6D125
0x6d0f2  ldarg.s  4
0x6d0f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d0f9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d0fe  brfalse.s loc_6D125
0x6d100  ldc.i4.1
0x6d101  stloc.1
0x6d102  ldloc.0
0x6d103  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d108  ldc.i4.1
0x6d109  newarr   [mscorlib]System.Object
0x6d10e  stloc.s  0xC
0x6d110  ldloc.s  0xC
0x6d112  ldc.i4.0
0x6d113  ldstr    aItemid// "itemId"
0x6d118  stelem.ref
0x6d119  ldloc.s  0xC
0x6d11b  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d120  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d125  ldloc.1
0x6d126  brtrue   loc_6D329
0x6d12b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6d130  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6d135  ldarg.s  7
0x6d137  ldarg.s  8
0x6d139  ldc.i4.1
0x6d13a  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6d13f  stloc.2
0x6d140  ldloc.2
0x6d141  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6d146  stloc.3
0x6d147  ldloc.3
0x6d148  ldarg.1
0x6d149  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6d14e  stloc.s  4
0x6d150  ldloc.s  4
0x6d152  ldarg.2
0x6d153  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6d158  ldarg.3
0x6d159  ldc.i4.1
0x6d15a  bne.un.s loc_6D196
0x6d15c  ldloc.s  4
0x6d15e  ldarg.s  4
0x6d160  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid id)
0x6d165  stloc.s  5
0x6d167  ldloc.s  5
0x6d169  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d16e  ldloc.s  5
0x6d170  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x6d175  ldarg.s  6
0x6d177  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6d17c  brfalse  loc_6D308
0x6d181  ldloc.s  5
0x6d183  ldarg.s  6
0x6d185  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::set_Name(string value)
0x6d18a  ldloc.s  4
0x6d18c  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d191  br       loc_6D308
0x6d196  ldarg.3
0x6d197  ldc.i4.3
0x6d198  beq.s    loc_6D19F
0x6d19a  ldarg.3
0x6d19b  ldc.i4.s 0xC
0x6d19d  bne.un.s loc_6D1D9
0x6d19f  ldloc.s  4
0x6d1a1  ldarg.s  4
0x6d1a3  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6d1a8  stloc.s  6
0x6d1aa  ldloc.s  6
0x6d1ac  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d1b1  ldloc.s  6
0x6d1b3  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x6d1b8  ldarg.s  6
0x6d1ba  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6d1bf  brfalse  loc_6D308
0x6d1c4  ldloc.s  6
0x6d1c6  ldarg.s  6
0x6d1c8  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::set_Name(string value)
0x6d1cd  ldloc.s  4
0x6d1cf  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d1d4  br       loc_6D308
0x6d1d9  ldarg.3
0x6d1da  ldc.i4.4
0x6d1db  beq.s    loc_6D1E9
0x6d1dd  ldarg.3
0x6d1de  ldc.i4.s 0xA
0x6d1e0  beq.s    loc_6D1E9
0x6d1e2  ldarg.3
0x6d1e3  ldc.i4.7
0x6d1e4  bne.un   loc_6D2E3
0x6d1e9  ldarg.s  5
0x6d1eb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d1f0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d1f5  brfalse.s loc_6D224
0x6d1f7  ldarg.3
0x6d1f8  ldc.i4.s 0xA
0x6d1fa  beq.s    loc_6D224
0x6d1fc  ldloc.0
0x6d1fd  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d202  ldc.i4.1
0x6d203  newarr   [mscorlib]System.Object
0x6d208  stloc.s  0xD
0x6d20a  ldloc.s  0xD
0x6d20c  ldc.i4.0
0x6d20d  ldstr    aParentid_0// "parentId"
0x6d212  stelem.ref
0x6d213  ldloc.s  0xD
0x6d215  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d21a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d21f  br       loc_6D308
0x6d224  ldarg.s  5
0x6d226  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d22b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d230  brfalse.s loc_6D23F
0x6d232  ldloc.s  4
0x6d234  ldarg.s  4
0x6d236  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termId)
0x6d23b  stloc.s  7
0x6d23d  br.s     loc_6D24C
0x6d23f  ldloc.s  4
0x6d241  ldarg.s  5
0x6d243  ldarg.s  4
0x6d245  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6d24a  stloc.s  7
0x6d24c  ldloc.s  7
0x6d24e  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d253  ldloc.s  7
0x6d255  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x6d25a  ldarg.s  6
0x6d25c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6d261  brfalse.s loc_6D278
0x6d263  ldarg.3
0x6d264  ldc.i4.s 0xA
0x6d266  beq.s    loc_6D278
0x6d268  ldloc.s  7
0x6d26a  ldarg.s  6
0x6d26c  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::set_Name(string value)
0x6d271  ldloc.s  4
0x6d273  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d278  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6d27d  stloc.s  8
0x6d27f  ldloc.s  7
0x6d281  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6d286  brfalse.s loc_6D2C6
0x6d288  ldloc.s  7
0x6d28a  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6d28f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6d294  stloc.s  0xE
0x6d296  br.s     loc_6D2AF
0x6d298  ldloc.s  0xE
0x6d29a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6d29f  stloc.s  9
0x6d2a1  ldloc.s  8
0x6d2a3  ldloc.s  9
0x6d2a5  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6d2aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6d2af  ldloc.s  0xE
0x6d2b1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6d2b6  brtrue.s loc_6D298
0x6d2b8  leave.s  loc_6D2C6
0x6d2ba  ldloc.s  0xE
0x6d2bc  brfalse.s loc_6D2C5
0x6d2be  ldloc.s  0xE
0x6d2c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d2c5  endfinally
0x6d2c6  ldarg.3
0x6d2c7  ldc.i4.s 0xA
0x6d2c9  bne.un.s loc_6D2D9
0x6d2cb  ldloc.s  8
0x6d2cd  ldloc.s  7
0x6d2cf  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6d2d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6d2d9  ldloc.0
0x6d2da  ldloc.s  8
0x6d2dc  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d2e1  br.s     loc_6D308
0x6d2e3  ldc.i4.1
0x6d2e4  stloc.1
0x6d2e5  ldloc.0
0x6d2e6  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d2eb  ldc.i4.1
0x6d2ec  newarr   [mscorlib]System.Object
0x6d2f1  stloc.s  0xF
0x6d2f3  ldloc.s  0xF
0x6d2f5  ldc.i4.0
0x6d2f6  ldstr    aItemtype// "itemType"
0x6d2fb  stelem.ref
0x6d2fc  ldloc.s  0xF
0x6d2fe  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d303  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d308  leave.s  loc_6D314
0x6d30a  ldloc.2
0x6d30b  brfalse.s loc_6D313
0x6d30d  ldloc.2
0x6d30e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d313  endfinally
0x6d314  leave.s  loc_6D329
0x6d316  stloc.s  0xA
0x6d318  ldc.i4.1
0x6d319  stloc.1
0x6d31a  ldloc.0
0x6d31b  ldloc.s  0xA
0x6d31d  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6d322  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d327  leave.s  loc_6D329
0x6d329  ldloc.1
0x6d32a  brtrue.s loc_6D357
0x6d32c  ldc.i4   0x360843
0x6d331  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6d336  ldc.i4.s 0x32
0x6d338  ldstr    aFeatureusageev_0// "FeatureUsageEvent: Successfully changed"...
0x6d33d  ldc.i4.1
0x6d33e  newarr   [mscorlib]System.Object
0x6d343  stloc.s  0x10
0x6d345  ldloc.s  0x10
0x6d347  ldc.i4.0
0x6d348  ldarg.s  4
0x6d34a  box      [mscorlib]System.Guid
0x6d34f  stelem.ref
0x6d350  ldloc.s  0x10
0x6d352  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6d357  ldloc.0
0x6d358  ret
```
