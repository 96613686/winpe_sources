# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ReuseTerm15

- ea: `0x6e150`
- end: `0x6e37c`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ReuseTerm15`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e130`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x48840`
- `0x497f0`
- `0x4ba10`
- `0x4d280`
- `0x4d290`
- `0x53f80`
- `0x546d0`
- `0x54710`
- `0x55050`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6df30`
- `0x6e150`
- `0x6ed70`
- `0x71160`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6e16b`: `TSMTWebServiceInvalidParam`
- `0x6e1a1`: `TSMTWebServiceInvalidParam`
- `0x6e1db`: `TSMTWebServiceInvalidParam`
- `0x6e301`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6e150  ldarg.s  9
0x6e152  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6e157  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6e15c  stloc.0
0x6e15d  ldarg.2
0x6e15e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e163  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e168  brfalse.s loc_6E192
0x6e16a  ldloc.0
0x6e16b  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e170  ldc.i4.1
0x6e171  newarr   [mscorlib]System.Object
0x6e176  stloc.s  8
0x6e178  ldloc.s  8
0x6e17a  ldc.i4.0
0x6e17b  ldstr    aParentid_0// "parentId"
0x6e180  stelem.ref
0x6e181  ldloc.s  8
0x6e183  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e188  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e18d  br       loc_6E342
0x6e192  ldarg.s  5
0x6e194  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e199  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e19e  brfalse.s loc_6E1C8
0x6e1a0  ldloc.0
0x6e1a1  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e1a6  ldc.i4.1
0x6e1a7  newarr   [mscorlib]System.Object
0x6e1ac  stloc.s  9
0x6e1ae  ldloc.s  9
0x6e1b0  ldc.i4.0
0x6e1b1  ldstr    aReusetermid// "reuseTermId"
0x6e1b6  stelem.ref
0x6e1b7  ldloc.s  9
0x6e1b9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e1be  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e1c3  br       loc_6E342
0x6e1c8  ldarg.3
0x6e1c9  ldc.i4.4
0x6e1ca  bne.un.s loc_6E202
0x6e1cc  ldarg.s  4
0x6e1ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e1d3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e1d8  brfalse.s loc_6E202
0x6e1da  ldloc.0
0x6e1db  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e1e0  ldc.i4.1
0x6e1e1  newarr   [mscorlib]System.Object
0x6e1e6  stloc.s  0xA
0x6e1e8  ldloc.s  0xA
0x6e1ea  ldc.i4.0
0x6e1eb  ldstr    aTermsetid_3// "termsetId"
0x6e1f0  stelem.ref
0x6e1f1  ldloc.s  0xA
0x6e1f3  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e1f8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e1fd  br       loc_6E342
0x6e202  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6e207  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6e20c  ldarg.s  7
0x6e20e  ldarg.s  8
0x6e210  ldc.i4.1
0x6e211  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6e216  stloc.1
0x6e217  ldloc.1
0x6e218  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6e21d  stloc.2
0x6e21e  ldloc.2
0x6e21f  ldarg.1
0x6e220  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6e225  stloc.3
0x6e226  ldloc.3
0x6e227  ldarg.s  9
0x6e229  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6e22e  ldarg.s  6
0x6e230  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e235  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e23a  brfalse.s loc_6E248
0x6e23c  ldloc.3
0x6e23d  ldarg.s  5
0x6e23f  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termId)
0x6e244  stloc.s  4
0x6e246  br.s     loc_6E254
0x6e248  ldloc.3
0x6e249  ldarg.s  6
0x6e24b  ldarg.s  5
0x6e24d  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6e252  stloc.s  4
0x6e254  ldloc.s  4
0x6e256  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e25b  ldloc.s  4
0x6e25d  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_ParentGroup()
0x6e262  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsReadOnlySiteCollectionGroup()
0x6e267  brfalse.s loc_6E26C
0x6e269  ldc.i4.1
0x6e26a  starg.s  0xA
0x6e26c  ldarg.3
0x6e26d  ldc.i4.3
0x6e26e  bne.un.s loc_6E2B1
0x6e270  ldloc.3
0x6e271  ldarg.2
0x6e272  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6e277  stloc.s  5
0x6e279  ldloc.s  5
0x6e27b  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e280  ldarg.s  0xA
0x6e282  brfalse.s loc_6E290
0x6e284  ldloc.s  5
0x6e286  ldloc.s  4
0x6e288  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTermWithPinning(class Microsoft.SharePoint.Taxonomy.Term sourceTerm)
0x6e28d  pop
0x6e28e  br.s     loc_6E29C
0x6e290  ldloc.s  5
0x6e292  ldloc.s  4
0x6e294  ldarg.s  0xB
0x6e296  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTerm(class Microsoft.SharePoint.Taxonomy.Term sourceTerm, bool reuseBranch)
0x6e29b  pop
0x6e29c  ldloc.0
0x6e29d  ldloc.s  4
0x6e29f  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6e2a4  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6e2a9  ldloc.3
0x6e2aa  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6e2af  br.s     loc_6E323
0x6e2b1  ldarg.3
0x6e2b2  ldc.i4.4
0x6e2b3  bne.un.s loc_6E300
0x6e2b5  ldloc.3
0x6e2b6  ldarg.s  4
0x6e2b8  ldarg.2
0x6e2b9  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6e2be  stloc.s  6
0x6e2c0  ldloc.s  6
0x6e2c2  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e2c7  ldarg.s  0xA
0x6e2c9  brfalse.s loc_6E2D7
0x6e2cb  ldloc.s  6
0x6e2cd  ldloc.s  4
0x6e2cf  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTermWithPinning(class Microsoft.SharePoint.Taxonomy.Term sourceTerm)
0x6e2d4  pop
0x6e2d5  br.s     loc_6E2E3
0x6e2d7  ldloc.s  6
0x6e2d9  ldloc.s  4
0x6e2db  ldarg.s  0xB
0x6e2dd  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::ReuseTerm(class Microsoft.SharePoint.Taxonomy.Term sourceTerm, bool reuseBranch)
0x6e2e2  pop
0x6e2e3  ldloc.0
0x6e2e4  ldloc.s  4
0x6e2e6  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6e2eb  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6e2f0  ldloc.0
0x6e2f1  ldloc.s  6
0x6e2f3  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GeneratePinData(class Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject returnVal, class Microsoft.SharePoint.Taxonomy.Term term)
0x6e2f8  ldloc.3
0x6e2f9  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6e2fe  br.s     loc_6E323
0x6e300  ldloc.0
0x6e301  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e306  ldc.i4.1
0x6e307  newarr   [mscorlib]System.Object
0x6e30c  stloc.s  0xB
0x6e30e  ldloc.s  0xB
0x6e310  ldc.i4.0
0x6e311  ldstr    aItemtype// "itemType"
0x6e316  stelem.ref
0x6e317  ldloc.s  0xB
0x6e319  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e31e  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e323  leave.s  loc_6E32F
0x6e325  ldloc.1
0x6e326  brfalse.s loc_6E32E
0x6e328  ldloc.1
0x6e329  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e32e  endfinally
0x6e32f  leave.s  loc_6E342
0x6e331  stloc.s  7
0x6e333  ldloc.0
0x6e334  ldloc.s  7
0x6e336  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6e33b  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e340  leave.s  loc_6E342
0x6e342  ldloc.0
0x6e343  callvirt instance string Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Error()
0x6e348  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e34d  brfalse.s loc_6E37A
0x6e34f  ldc.i4   0x360848
0x6e354  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6e359  ldc.i4.s 0x32
0x6e35b  ldstr    aFeatureusageev_5// "FeatureUsageEvent: Successfully reused "...
0x6e360  ldc.i4.1
0x6e361  newarr   [mscorlib]System.Object
0x6e366  stloc.s  0xC
0x6e368  ldloc.s  0xC
0x6e36a  ldc.i4.0
0x6e36b  ldarg.s  5
0x6e36d  box      [mscorlib]System.Guid
0x6e372  stelem.ref
0x6e373  ldloc.s  0xC
0x6e375  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6e37a  ldloc.0
0x6e37b  ret
```
