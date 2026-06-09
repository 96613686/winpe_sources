# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MoveTaxonomyItem15

- ea: `0x6e3b0`
- end: `0x6e6dc`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MoveTaxonomyItem15`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e380`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x4f1e0`
- `0x4f560`
- `0x52c30`
- `0x53f80`
- `0x545b0`
- `0x54710`
- `0x55050`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6e040`
- `0x6e060`
- `0x6e3b0`
- `0x6e6e0`
- `0x6e7e0`
- `0x6fa50`
- `0x71160`
- `0x71170`
- `0x71190`
- `0x711b0`
- `0x71200`

## string_xrefs

- `0x6e3cb`: `TSMTWebServiceInvalidParam`
- `0x6e401`: `TSMTWebServiceInvalidParam`
- `0x6e43b`: `TSMTWebServiceInvalidParam`
- `0x6e476`: `TSMTWebServiceInvalidParam`
- `0x6e55a`: `TSMTWebServiceInvalidParam`
- `0x6e615`: `TSMTWebServiceInvalidParam`
- `0x6e63a`: `TSMTWebServiceInvalidParam`
- `0x6e6bc`: `FeatureUsageEvent: Successfully moved taxonomy item {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6e3b0  ldarg.s  0xF
0x6e3b2  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6e3b7  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6e3bc  stloc.0
0x6e3bd  ldarg.3
0x6e3be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e3c3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e3c8  brfalse.s loc_6E3F2
0x6e3ca  ldloc.0
0x6e3cb  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e3d0  ldc.i4.1
0x6e3d1  newarr   [mscorlib]System.Object
0x6e3d6  stloc.s  0xA
0x6e3d8  ldloc.s  0xA
0x6e3da  ldc.i4.0
0x6e3db  ldstr    aItemid// "itemId"
0x6e3e0  stelem.ref
0x6e3e1  ldloc.s  0xA
0x6e3e3  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e3e8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e3ed  br       loc_6E6A3
0x6e3f2  ldarg.s  6
0x6e3f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e3f9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e3fe  brfalse.s loc_6E428
0x6e400  ldloc.0
0x6e401  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e406  ldc.i4.1
0x6e407  newarr   [mscorlib]System.Object
0x6e40c  stloc.s  0xB
0x6e40e  ldloc.s  0xB
0x6e410  ldc.i4.0
0x6e411  ldstr    aParentid_0// "parentId"
0x6e416  stelem.ref
0x6e417  ldloc.s  0xB
0x6e419  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e41e  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e423  br       loc_6E6A3
0x6e428  ldarg.2
0x6e429  ldc.i4.4
0x6e42a  bne.un.s loc_6E462
0x6e42c  ldarg.s  4
0x6e42e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e433  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e438  brfalse.s loc_6E462
0x6e43a  ldloc.0
0x6e43b  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e440  ldc.i4.1
0x6e441  newarr   [mscorlib]System.Object
0x6e446  stloc.s  0xC
0x6e448  ldloc.s  0xC
0x6e44a  ldc.i4.0
0x6e44b  ldstr    aItemtermsetid// "itemTermsetId"
0x6e450  stelem.ref
0x6e451  ldloc.s  0xC
0x6e453  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e458  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e45d  br       loc_6E6A3
0x6e462  ldarg.s  5
0x6e464  ldc.i4.4
0x6e465  bne.un.s loc_6E49D
0x6e467  ldarg.s  7
0x6e469  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e46e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e473  brfalse.s loc_6E49D
0x6e475  ldloc.0
0x6e476  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e47b  ldc.i4.1
0x6e47c  newarr   [mscorlib]System.Object
0x6e481  stloc.s  0xD
0x6e483  ldloc.s  0xD
0x6e485  ldc.i4.0
0x6e486  ldstr    aParenttermseti// "parentTermsetId"
0x6e48b  stelem.ref
0x6e48c  ldloc.s  0xD
0x6e48e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e493  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e498  br       loc_6E6A3
0x6e49d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6e4a2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6e4a7  ldarg.s  0xD
0x6e4a9  ldarg.s  0xE
0x6e4ab  ldc.i4.1
0x6e4ac  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6e4b1  stloc.1
0x6e4b2  ldloc.1
0x6e4b3  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6e4b8  stloc.2
0x6e4b9  ldloc.2
0x6e4ba  ldarg.1
0x6e4bb  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6e4c0  stloc.3
0x6e4c1  ldloc.3
0x6e4c2  ldarg.s  0xF
0x6e4c4  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6e4c9  ldarg.2
0x6e4ca  ldc.i4.4
0x6e4cb  beq.s    loc_6E4D4
0x6e4cd  ldarg.2
0x6e4ce  ldc.i4.7
0x6e4cf  bne.un   loc_6E5CC
0x6e4d4  ldloc.3
0x6e4d5  ldarg.s  4
0x6e4d7  ldarg.3
0x6e4d8  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6e4dd  stloc.s  4
0x6e4df  ldloc.s  4
0x6e4e1  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e4e6  ldarg.s  9
0x6e4e8  brfalse.s loc_6E509
0x6e4ea  ldarg.s  0xC
0x6e4ec  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e4f1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e4f6  brfalse.s loc_6E509
0x6e4f8  ldloc.0
0x6e4f9  ldloc.s  4
0x6e4fb  ldarg.s  0xA
0x6e4fd  ldarg.s  0xB
0x6e4ff  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetNextDisplayPageItems(class Microsoft.SharePoint.Taxonomy.Term term, int32 pageLimit, bool includeDeprecated)
0x6e504  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6e509  ldnull
0x6e50a  stloc.s  5
0x6e50c  ldloc.s  4
0x6e50e  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6e513  stloc.s  6
0x6e515  ldloc.s  6
0x6e517  brtrue.s loc_6E529
0x6e519  ldloc.s  4
0x6e51b  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6e520  stloc.s  5
0x6e522  ldloc.s  5
0x6e524  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e529  ldarg.s  5
0x6e52b  ldc.i4.4
0x6e52c  bne.un.s loc_6E53F
0x6e52e  ldloc.3
0x6e52f  ldarg.s  6
0x6e531  ldarg.s  7
0x6e533  ldloc.s  4
0x6e535  ldarg.s  8
0x6e537  ldloc.0
0x6e538  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MoveNotRootTerm(class Microsoft.SharePoint.Taxonomy.TermStore termStore, valuetype [mscorlib]System.Guid parentId, valuetype [mscorlib]System.Guid parentTermsetId, class Microsoft.SharePoint.Taxonomy.Term term, int32 rootNodeType, class Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject returnVal)
0x6e53d  br.s     loc_6E57C
0x6e53f  ldarg.s  5
0x6e541  ldc.i4.3
0x6e542  beq.s    loc_6E54A
0x6e544  ldarg.s  5
0x6e546  ldc.i4.s 0xC
0x6e548  bne.un.s loc_6E559
0x6e54a  ldloc.3
0x6e54b  ldarg.s  6
0x6e54d  ldloc.s  4
0x6e54f  ldarg.s  0x10
0x6e551  ldloc.0
0x6e552  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MoveRootTerm(class Microsoft.SharePoint.Taxonomy.TermStore termStore, valuetype [mscorlib]System.Guid parentId, class Microsoft.SharePoint.Taxonomy.Term term, bool blocksKeyword, class Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject returnVal)
0x6e557  br.s     loc_6E57C
0x6e559  ldloc.0
0x6e55a  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e55f  ldc.i4.1
0x6e560  newarr   [mscorlib]System.Object
0x6e565  stloc.s  0xE
0x6e567  ldloc.s  0xE
0x6e569  ldc.i4.0
0x6e56a  ldstr    aParenttype// "parentType"
0x6e56f  stelem.ref
0x6e570  ldloc.s  0xE
0x6e572  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e577  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e57c  ldarg.s  9
0x6e57e  brfalse  loc_6E65C
0x6e583  ldarg.s  0xC
0x6e585  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e58a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e58f  brfalse  loc_6E65C
0x6e594  ldloc.s  6
0x6e596  brfalse.s loc_6E5B2
0x6e598  ldloc.0
0x6e599  ldloc.s  6
0x6e59b  ldarg.s  0xA
0x6e59d  ldc.i4.1
0x6e59e  ldarg.s  0xC
0x6e5a0  ldc.i4.1
0x6e5a1  ldarg.s  0xB
0x6e5a3  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6e5a8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6e5ad  br       loc_6E65C
0x6e5b2  ldloc.0
0x6e5b3  ldloc.s  5
0x6e5b5  ldarg.s  0xA
0x6e5b7  ldc.i4.1
0x6e5b8  ldarg.s  0xC
0x6e5ba  ldc.i4.1
0x6e5bb  ldarg.s  0xB
0x6e5bd  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6e5c2  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6e5c7  br       loc_6E65C
0x6e5cc  ldarg.2
0x6e5cd  ldc.i4.3
0x6e5ce  bne.un.s loc_6E639
0x6e5d0  ldloc.3
0x6e5d1  ldarg.3
0x6e5d2  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6e5d7  stloc.s  7
0x6e5d9  ldloc.s  7
0x6e5db  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e5e0  ldarg.s  5
0x6e5e2  ldc.i4.1
0x6e5e3  bne.un.s loc_6E614
0x6e5e5  ldloc.3
0x6e5e6  ldarg.s  6
0x6e5e8  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid id)
0x6e5ed  stloc.s  8
0x6e5ef  ldloc.s  8
0x6e5f1  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e5f6  ldloc.s  7
0x6e5f8  ldloc.s  8
0x6e5fa  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSet::Move(class Microsoft.SharePoint.Taxonomy.Group targetGroup)
0x6e5ff  ldloc.3
0x6e600  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6e605  ldloc.0
0x6e606  ldloc.s  8
0x6e608  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildGroupPath(class Microsoft.SharePoint.Taxonomy.Group group)
0x6e60d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_OtherData(object value)
0x6e612  br.s     loc_6E65C
0x6e614  ldloc.0
0x6e615  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e61a  ldc.i4.1
0x6e61b  newarr   [mscorlib]System.Object
0x6e620  stloc.s  0xF
0x6e622  ldloc.s  0xF
0x6e624  ldc.i4.0
0x6e625  ldstr    aParenttype// "parentType"
0x6e62a  stelem.ref
0x6e62b  ldloc.s  0xF
0x6e62d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e632  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e637  br.s     loc_6E65C
0x6e639  ldloc.0
0x6e63a  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e63f  ldc.i4.1
0x6e640  newarr   [mscorlib]System.Object
0x6e645  stloc.s  0x10
0x6e647  ldloc.s  0x10
0x6e649  ldc.i4.0
0x6e64a  ldstr    aItemtype// "itemType"
0x6e64f  stelem.ref
0x6e650  ldloc.s  0x10
0x6e652  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e657  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e65c  leave.s  loc_6E668
0x6e65e  ldloc.1
0x6e65f  brfalse.s loc_6E667
0x6e661  ldloc.1
0x6e662  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e667  endfinally
0x6e668  leave.s  loc_6E6A3
0x6e66a  stloc.s  9
0x6e66c  ldloc.s  9
0x6e66e  isinst   [mscorlib]System.ArgumentException
0x6e673  brfalse.s loc_6E694
0x6e675  ldloc.s  9
0x6e677  isinst   [mscorlib]System.ArgumentNullException
0x6e67c  brtrue.s loc_6E694
0x6e67e  ldloc.s  9
0x6e680  isinst   [mscorlib]System.ArgumentOutOfRangeException
0x6e685  brtrue.s loc_6E694
0x6e687  ldloc.0
0x6e688  ldloc.s  9
0x6e68a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6e68f  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e694  ldloc.0
0x6e695  ldloc.s  9
0x6e697  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6e69c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e6a1  leave.s  loc_6E6A3
0x6e6a3  ldloc.0
0x6e6a4  callvirt instance string Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Error()
0x6e6a9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6e6ae  brfalse.s loc_6E6DA
0x6e6b0  ldc.i4   0x360849
0x6e6b5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6e6ba  ldc.i4.s 0x32
0x6e6bc  ldstr    aFeatureusageev_6// "FeatureUsageEvent: Successfully moved t"...
0x6e6c1  ldc.i4.1
0x6e6c2  newarr   [mscorlib]System.Object
0x6e6c7  stloc.s  0x11
0x6e6c9  ldloc.s  0x11
0x6e6cb  ldc.i4.0
0x6e6cc  ldarg.3
0x6e6cd  box      [mscorlib]System.Guid
0x6e6d2  stelem.ref
0x6e6d3  ldloc.s  0x11
0x6e6d5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6e6da  ldloc.0
0x6e6db  ret
```
