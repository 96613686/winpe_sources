# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MergeTaxonomyItem

- ea: `0x6e8d0`
- end: `0x6ebc6`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::MergeTaxonomyItem`
- size: `758`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x4e570`
- `0x4f1e0`
- `0x4f3a0`
- `0x4f560`
- `0x53f80`
- `0x54710`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6df30`
- `0x6dfe0`
- `0x6e8d0`
- `0x6fa50`
- `0x710d0`
- `0x710f0`
- `0x71140`
- `0x71160`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6e8ea`: `TSMTWebServiceInvalidParam`
- `0x6e920`: `TSMTWebServiceInvalidParam`
- `0x6e956`: `TSMTWebServiceInvalidParam`
- `0x6e98c`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6e8d0  ldarg.2
0x6e8d1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6e8d6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6e8db  stloc.0
0x6e8dc  ldarg.3
0x6e8dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e8e2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e8e7  brfalse.s loc_6E911
0x6e8e9  ldloc.0
0x6e8ea  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e8ef  ldc.i4.1
0x6e8f0  newarr   [mscorlib]System.Object
0x6e8f5  stloc.s  0xE
0x6e8f7  ldloc.s  0xE
0x6e8f9  ldc.i4.0
0x6e8fa  ldstr    aMergesourceid// "mergeSourceId"
0x6e8ff  stelem.ref
0x6e900  ldloc.s  0xE
0x6e902  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e907  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e90c  br       loc_6EB82
0x6e911  ldarg.s  4
0x6e913  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e918  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e91d  brfalse.s loc_6E947
0x6e91f  ldloc.0
0x6e920  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e925  ldc.i4.1
0x6e926  newarr   [mscorlib]System.Object
0x6e92b  stloc.s  0xF
0x6e92d  ldloc.s  0xF
0x6e92f  ldc.i4.0
0x6e930  ldstr    aMergesourceter// "mergeSourceTermsetId"
0x6e935  stelem.ref
0x6e936  ldloc.s  0xF
0x6e938  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e93d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e942  br       loc_6EB82
0x6e947  ldarg.s  5
0x6e949  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e94e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e953  brfalse.s loc_6E97D
0x6e955  ldloc.0
0x6e956  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e95b  ldc.i4.1
0x6e95c  newarr   [mscorlib]System.Object
0x6e961  stloc.s  0x10
0x6e963  ldloc.s  0x10
0x6e965  ldc.i4.0
0x6e966  ldstr    aMergetargetid// "mergeTargetId"
0x6e96b  stelem.ref
0x6e96c  ldloc.s  0x10
0x6e96e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e973  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e978  br       loc_6EB82
0x6e97d  ldarg.s  6
0x6e97f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e984  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6e989  brfalse.s loc_6E9B3
0x6e98b  ldloc.0
0x6e98c  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6e991  ldc.i4.1
0x6e992  newarr   [mscorlib]System.Object
0x6e997  stloc.s  0x11
0x6e999  ldloc.s  0x11
0x6e99b  ldc.i4.0
0x6e99c  ldstr    aMergetargetter// "mergeTargetTermsetId"
0x6e9a1  stelem.ref
0x6e9a2  ldloc.s  0x11
0x6e9a4  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6e9a9  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6e9ae  br       loc_6EB82
0x6e9b3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6e9b8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6e9bd  ldarg.s  9
0x6e9bf  ldarg.s  0xA
0x6e9c1  ldc.i4.1
0x6e9c2  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6e9c7  stloc.1
0x6e9c8  ldloc.1
0x6e9c9  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6e9ce  stloc.2
0x6e9cf  ldloc.2
0x6e9d0  ldarg.1
0x6e9d1  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6e9d6  stloc.3
0x6e9d7  ldloc.3
0x6e9d8  ldarg.2
0x6e9d9  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6e9de  ldloc.3
0x6e9df  ldarg.s  4
0x6e9e1  ldarg.3
0x6e9e2  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6e9e7  stloc.s  4
0x6e9e9  ldloc.s  4
0x6e9eb  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6e9f0  ldloc.3
0x6e9f1  ldarg.s  6
0x6e9f3  ldarg.s  5
0x6e9f5  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6e9fa  stloc.s  5
0x6e9fc  ldloc.s  5
0x6e9fe  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6ea03  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::.ctor()
0x6ea08  stloc.s  6
0x6ea0a  ldloc.s  4
0x6ea0c  ldloc.s  5
0x6ea0e  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::Merge(class Microsoft.SharePoint.Taxonomy.Term termToMerge)
0x6ea13  stloc.s  7
0x6ea15  ldloc.3
0x6ea16  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6ea1b  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::.ctor()
0x6ea20  stloc.s  8
0x6ea22  ldloc.s  7
0x6ea24  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6ea29  stloc.s  9
0x6ea2b  ldloc.s  9
0x6ea2d  brtrue.s loc_6EA6A
0x6ea2f  ldloc.s  7
0x6ea31  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6ea36  stloc.s  0xA
0x6ea38  ldloc.s  8
0x6ea3a  ldloc.s  0xA
0x6ea3c  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermSetPath(class Microsoft.SharePoint.Taxonomy.TermSet termset)
0x6ea41  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::set_PId(string value)
0x6ea46  ldloc.s  8
0x6ea48  ldloc.s  0xA
0x6ea4a  ldarg.s  7
0x6ea4c  ldc.i4.1
0x6ea4d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ea52  ldc.i4.1
0x6ea53  ldarg.s  8
0x6ea55  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6ea5a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::AddChildCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> childCollection)
0x6ea5f  ldloc.s  6
0x6ea61  ldloc.s  8
0x6ea63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::Add(var<u1>)
0x6ea68  br.s     loc_6EA9A
0x6ea6a  ldloc.s  8
0x6ea6c  ldloc.s  9
0x6ea6e  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6ea73  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::set_PId(string value)
0x6ea78  ldloc.s  8
0x6ea7a  ldloc.s  9
0x6ea7c  ldarg.s  7
0x6ea7e  ldc.i4.1
0x6ea7f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ea84  ldc.i4.1
0x6ea85  ldarg.s  8
0x6ea87  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6ea8c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::AddChildCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> childCollection)
0x6ea91  ldloc.s  6
0x6ea93  ldloc.s  8
0x6ea95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::Add(var<u1>)
0x6ea9a  ldloc.s  7
0x6ea9c  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6eaa1  brfalse  loc_6EB5B
0x6eaa6  ldloc.s  7
0x6eaa8  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6eaad  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6eab2  stloc.s  0x12
0x6eab4  br       loc_6EB41
0x6eab9  ldloc.s  0x12
0x6eabb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6eac0  stloc.s  0xB
0x6eac2  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::.ctor()
0x6eac7  stloc.s  8
0x6eac9  ldloc.s  0xB
0x6eacb  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6ead0  stloc.s  9
0x6ead2  ldloc.s  9
0x6ead4  brtrue.s loc_6EB11
0x6ead6  ldloc.s  0xB
0x6ead8  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6eadd  stloc.s  0xC
0x6eadf  ldloc.s  8
0x6eae1  ldloc.s  0xC
0x6eae3  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermSetPath(class Microsoft.SharePoint.Taxonomy.TermSet termset)
0x6eae8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::set_PId(string value)
0x6eaed  ldloc.s  8
0x6eaef  ldloc.s  0xC
0x6eaf1  ldarg.s  7
0x6eaf3  ldc.i4.1
0x6eaf4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6eaf9  ldc.i4.1
0x6eafa  ldarg.s  8
0x6eafc  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6eb01  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::AddChildCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> childCollection)
0x6eb06  ldloc.s  6
0x6eb08  ldloc.s  8
0x6eb0a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::Add(var<u1>)
0x6eb0f  br.s     loc_6EB41
0x6eb11  ldloc.s  8
0x6eb13  ldloc.s  9
0x6eb15  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6eb1a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::set_PId(string value)
0x6eb1f  ldloc.s  8
0x6eb21  ldloc.s  9
0x6eb23  ldarg.s  7
0x6eb25  ldc.i4.1
0x6eb26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6eb2b  ldc.i4.1
0x6eb2c  ldarg.s  8
0x6eb2e  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6eb33  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::AddChildCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> childCollection)
0x6eb38  ldloc.s  6
0x6eb3a  ldloc.s  8
0x6eb3c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::Add(var<u1>)
0x6eb41  ldloc.s  0x12
0x6eb43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6eb48  brtrue   loc_6EAB9
0x6eb4d  leave.s  loc_6EB5B
0x6eb4f  ldloc.s  0x12
0x6eb51  brfalse.s loc_6EB5A
0x6eb53  ldloc.s  0x12
0x6eb55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eb5a  endfinally
0x6eb5b  ldloc.0
0x6eb5c  ldloc.s  6
0x6eb5e  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6eb63  leave.s  loc_6EB6F
0x6eb65  ldloc.1
0x6eb66  brfalse.s loc_6EB6E
0x6eb68  ldloc.1
0x6eb69  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eb6e  endfinally
0x6eb6f  leave.s  loc_6EB82
0x6eb71  stloc.s  0xD
0x6eb73  ldloc.0
0x6eb74  ldloc.s  0xD
0x6eb76  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6eb7b  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6eb80  leave.s  loc_6EB82
0x6eb82  ldloc.0
0x6eb83  callvirt instance string Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Error()
0x6eb88  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6eb8d  brfalse.s loc_6EBC4
0x6eb8f  ldc.i4   0x36084A
0x6eb94  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6eb99  ldc.i4.s 0x32
0x6eb9b  ldstr    aFeatureusageev_7// "FeatureUsageEvent: Successfully merged "...
0x6eba0  ldc.i4.2
0x6eba1  newarr   [mscorlib]System.Object
0x6eba6  stloc.s  0x13
0x6eba8  ldloc.s  0x13
0x6ebaa  ldc.i4.0
0x6ebab  ldarg.3
0x6ebac  box      [mscorlib]System.Guid
0x6ebb1  stelem.ref
0x6ebb2  ldloc.s  0x13
0x6ebb4  ldc.i4.1
0x6ebb5  ldarg.s  5
0x6ebb7  box      [mscorlib]System.Guid
0x6ebbc  stelem.ref
0x6ebbd  ldloc.s  0x13
0x6ebbf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6ebc4  ldloc.0
0x6ebc5  ret
```
