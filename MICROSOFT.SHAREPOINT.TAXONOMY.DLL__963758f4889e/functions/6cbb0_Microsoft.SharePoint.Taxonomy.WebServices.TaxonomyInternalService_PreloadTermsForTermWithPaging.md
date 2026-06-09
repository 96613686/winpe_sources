# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::PreloadTermsForTermWithPaging

- ea: `0x6cbb0`
- end: `0x6cd12`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::PreloadTermsForTermWithPaging`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x48810`
- `0x4ba10`
- `0x4d550`
- `0x54710`
- `0x55610`
- `0x6cbb0`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6fa50`
- `0x710d0`
- `0x710f0`
- `0x71140`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6cbca`: `TSMTWebServiceInvalidParam`
- `0x6cc00`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6cbb0  ldarg.2
0x6cbb1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6cbb6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6cbbb  stloc.0
0x6cbbc  ldarg.3
0x6cbbd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cbc2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6cbc7  brfalse.s loc_6CBF1
0x6cbc9  ldloc.0
0x6cbca  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cbcf  ldc.i4.1
0x6cbd0  newarr   [mscorlib]System.Object
0x6cbd5  stloc.s  0xA
0x6cbd7  ldloc.s  0xA
0x6cbd9  ldc.i4.0
0x6cbda  ldstr    aGuid// "guid"
0x6cbdf  stelem.ref
0x6cbe0  ldloc.s  0xA
0x6cbe2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cbe7  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cbec  br       loc_6CD10
0x6cbf1  ldarg.s  4
0x6cbf3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cbf8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6cbfd  brfalse.s loc_6CC27
0x6cbff  ldloc.0
0x6cc00  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cc05  ldc.i4.1
0x6cc06  newarr   [mscorlib]System.Object
0x6cc0b  stloc.s  0xB
0x6cc0d  ldloc.s  0xB
0x6cc0f  ldc.i4.0
0x6cc10  ldstr    aTermsetid_3// "termsetId"
0x6cc15  stelem.ref
0x6cc16  ldloc.s  0xB
0x6cc18  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cc1d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cc22  br       loc_6CD10
0x6cc27  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6cc2c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6cc31  ldarg.s  7
0x6cc33  ldarg.s  8
0x6cc35  ldc.i4.1
0x6cc36  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6cc3b  stloc.1
0x6cc3c  ldloc.1
0x6cc3d  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6cc42  stloc.2
0x6cc43  ldloc.2
0x6cc44  ldarg.1
0x6cc45  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6cc4a  stloc.3
0x6cc4b  ldloc.3
0x6cc4c  ldarg.2
0x6cc4d  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6cc52  ldloc.3
0x6cc53  ldarg.s  4
0x6cc55  ldarg.3
0x6cc56  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6cc5b  stloc.s  4
0x6cc5d  ldloc.s  4
0x6cc5f  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6cc64  ldloc.s  4
0x6cc66  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermSetItem::get_Terms()
0x6cc6b  stloc.s  5
0x6cc6d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::.ctor()
0x6cc72  stloc.s  6
0x6cc74  ldloc.s  5
0x6cc76  brfalse.s loc_6CCE9
0x6cc78  ldloc.s  5
0x6cc7a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6cc7f  stloc.s  0xC
0x6cc81  br.s     loc_6CCD2
0x6cc83  ldloc.s  0xC
0x6cc85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6cc8a  stloc.s  7
0x6cc8c  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::.ctor()
0x6cc91  stloc.s  8
0x6cc93  ldloc.s  8
0x6cc95  ldloc.s  7
0x6cc97  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6cc9c  stloc.s  0xD
0x6cc9e  ldloca.s 0xD
0x6cca0  constrained. [mscorlib]System.Guid
0x6cca6  callvirt instance string [mscorlib]System.Object::ToString()
0x6ccab  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::set_PId(string value)
0x6ccb0  ldloc.s  8
0x6ccb2  ldloc.s  7
0x6ccb4  ldarg.s  6
0x6ccb6  ldc.i4.1
0x6ccb7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ccbc  ldc.i4.1
0x6ccbd  ldarg.s  5
0x6ccbf  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6ccc4  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent::AddChildCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> childCollection)
0x6ccc9  ldloc.s  6
0x6cccb  ldloc.s  8
0x6cccd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent>::Add(var<u1>)
0x6ccd2  ldloc.s  0xC
0x6ccd4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6ccd9  brtrue.s loc_6CC83
0x6ccdb  leave.s  loc_6CCE9
0x6ccdd  ldloc.s  0xC
0x6ccdf  brfalse.s loc_6CCE8
0x6cce1  ldloc.s  0xC
0x6cce3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cce8  endfinally
0x6cce9  ldloc.0
0x6ccea  ldloc.s  6
0x6ccec  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6ccf1  leave.s  loc_6CCFD
0x6ccf3  ldloc.1
0x6ccf4  brfalse.s loc_6CCFC
0x6ccf6  ldloc.1
0x6ccf7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ccfc  endfinally
0x6ccfd  leave.s  loc_6CD10
0x6ccff  stloc.s  9
0x6cd01  ldloc.0
0x6cd02  ldloc.s  9
0x6cd04  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6cd09  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cd0e  leave.s  loc_6CD10
0x6cd10  ldloc.0
0x6cd11  ret
```
