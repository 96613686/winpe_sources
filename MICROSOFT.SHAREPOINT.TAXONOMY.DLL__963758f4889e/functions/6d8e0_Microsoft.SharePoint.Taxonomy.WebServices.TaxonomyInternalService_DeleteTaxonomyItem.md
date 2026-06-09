# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::DeleteTaxonomyItem

- ea: `0x6d8e0`
- end: `0x6dc1c`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::DeleteTaxonomyItem`
- size: `828`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x48780`
- `0x48810`
- `0x4ba10`
- `0x4f1e0`
- `0x4f360`
- `0x4f3a0`
- `0x4f560`
- `0x53f80`
- `0x545b0`
- `0x54710`
- `0x55050`
- `0x55610`
- `0x6d530`
- `0x6d8e0`
- `0x6de50`
- `0x6deb0`
- `0x6df30`
- `0x6dfe0`
- `0x6e060`
- `0x6fa50`
- `0x71160`
- `0x71170`
- `0x71190`
- `0x711b0`
- `0x711d0`
- `0x71200`

## string_xrefs

- `0x6d8fa`: `TSMTWebServiceInvalidParam`
- `0x6d930`: `TSMTWebServiceInvalidParam`
- `0x6d96a`: `TSMTWebServiceInvalidParam`
- `0x6dba1`: `TSMTWebServiceInvalidParam`
- `0x6dbfb`: `FeatureUsageEvent: Successfully deleted taxonomy item {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6d8e0  ldarg.2
0x6d8e1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6d8e6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6d8eb  stloc.0
0x6d8ec  ldarg.1
0x6d8ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d8f2  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d8f7  brfalse.s loc_6D921
0x6d8f9  ldloc.0
0x6d8fa  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d8ff  ldc.i4.1
0x6d900  newarr   [mscorlib]System.Object
0x6d905  stloc.s  0xD
0x6d907  ldloc.s  0xD
0x6d909  ldc.i4.0
0x6d90a  ldstr    aSspid// "sspId"
0x6d90f  stelem.ref
0x6d910  ldloc.s  0xD
0x6d912  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d917  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d91c  br       loc_6DBE2
0x6d921  ldarg.s  4
0x6d923  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d928  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d92d  brfalse.s loc_6D957
0x6d92f  ldloc.0
0x6d930  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d935  ldc.i4.1
0x6d936  newarr   [mscorlib]System.Object
0x6d93b  stloc.s  0xE
0x6d93d  ldloc.s  0xE
0x6d93f  ldc.i4.0
0x6d940  ldstr    aItemid// "itemId"
0x6d945  stelem.ref
0x6d946  ldloc.s  0xE
0x6d948  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d94d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d952  br       loc_6DBE2
0x6d957  ldarg.3
0x6d958  ldc.i4.4
0x6d959  bne.un.s loc_6D991
0x6d95b  ldarg.s  5
0x6d95d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d962  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d967  brfalse.s loc_6D991
0x6d969  ldloc.0
0x6d96a  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d96f  ldc.i4.1
0x6d970  newarr   [mscorlib]System.Object
0x6d975  stloc.s  0xF
0x6d977  ldloc.s  0xF
0x6d979  ldc.i4.0
0x6d97a  ldstr    aTermsetid_3// "termsetId"
0x6d97f  stelem.ref
0x6d980  ldloc.s  0xF
0x6d982  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d987  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d98c  br       loc_6DBE2
0x6d991  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6d996  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6d99b  ldarg.s  0xA
0x6d99d  ldarg.s  0xB
0x6d99f  ldc.i4.1
0x6d9a0  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6d9a5  stloc.1
0x6d9a6  ldloc.1
0x6d9a7  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6d9ac  stloc.2
0x6d9ad  ldloc.2
0x6d9ae  ldarg.1
0x6d9af  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6d9b4  stloc.3
0x6d9b5  ldloc.3
0x6d9b6  ldarg.2
0x6d9b7  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6d9bc  ldarg.3
0x6d9bd  ldc.i4.1
0x6d9be  bne.un.s loc_6D9E3
0x6d9c0  ldloc.3
0x6d9c1  ldarg.s  4
0x6d9c3  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid id)
0x6d9c8  stloc.s  4
0x6d9ca  ldloc.s  4
0x6d9cc  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d9d1  ldloc.s  4
0x6d9d3  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x6d9d8  ldloc.3
0x6d9d9  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d9de  br       loc_6DBC3
0x6d9e3  ldarg.3
0x6d9e4  ldc.i4.3
0x6d9e5  bne.un.s loc_6DA0A
0x6d9e7  ldloc.3
0x6d9e8  ldarg.s  4
0x6d9ea  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6d9ef  stloc.s  5
0x6d9f1  ldloc.s  5
0x6d9f3  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d9f8  ldloc.s  5
0x6d9fa  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x6d9ff  ldloc.3
0x6da00  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6da05  br       loc_6DBC3
0x6da0a  ldarg.3
0x6da0b  ldc.i4.4
0x6da0c  beq.s    loc_6DA15
0x6da0e  ldarg.3
0x6da0f  ldc.i4.7
0x6da10  bne.un   loc_6DBA0
0x6da15  ldloc.3
0x6da16  ldarg.s  5
0x6da18  ldarg.s  4
0x6da1a  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6da1f  stloc.s  6
0x6da21  ldloc.s  6
0x6da23  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6da28  ldloc.s  6
0x6da2a  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6da2f  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x6da34  ldc.i4.0
0x6da35  ble      loc_6DAFD
0x6da3a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6da3f  stloc.s  7
0x6da41  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6da46  stloc.s  8
0x6da48  ldloc.s  6
0x6da4a  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6da4f  brfalse  loc_6DAED
0x6da54  ldloc.s  6
0x6da56  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.Term::get_ReusedTerms()
0x6da5b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6da60  stloc.s  0x10
0x6da62  br.s     loc_6DAD6
0x6da64  ldloc.s  0x10
0x6da66  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6da6b  stloc.s  9
0x6da6d  ldloc.s  9
0x6da6f  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_PinSourceTermSet()
0x6da74  brfalse.s loc_6DAC8
0x6da76  ldloc.s  9
0x6da78  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_PinSourceTermSet()
0x6da7d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6da82  ldloc.s  6
0x6da84  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6da89  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6da8e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6da93  brfalse.s loc_6DAC8
0x6da95  ldloc.s  9
0x6da97  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6da9c  brfalse.s loc_6DAB3
0x6da9e  ldloc.s  8
0x6daa0  ldloc.s  9
0x6daa2  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6daa7  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6daac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6dab1  br.s     loc_6DAD6
0x6dab3  ldloc.s  8
0x6dab5  ldloc.s  9
0x6dab7  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6dabc  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermSetPath(class Microsoft.SharePoint.Taxonomy.TermSet termset)
0x6dac1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6dac6  br.s     loc_6DAD6
0x6dac8  ldloc.s  7
0x6daca  ldloc.s  9
0x6dacc  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6dad1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6dad6  ldloc.s  0x10
0x6dad8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6dadd  brtrue.s loc_6DA64
0x6dadf  leave.s  loc_6DAED
0x6dae1  ldloc.s  0x10
0x6dae3  brfalse.s loc_6DAEC
0x6dae5  ldloc.s  0x10
0x6dae7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6daec  endfinally
0x6daed  ldloc.0
0x6daee  ldloc.s  7
0x6daf0  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_OtherData(object value)
0x6daf5  ldloc.0
0x6daf6  ldloc.s  8
0x6daf8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_PinData(object value)
0x6dafd  ldarg.s  6
0x6daff  brfalse  loc_6DB91
0x6db04  ldarg.s  9
0x6db06  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6db0b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6db10  brfalse.s loc_6DB71
0x6db12  ldnull
0x6db13  stloc.s  0xA
0x6db15  ldloc.s  6
0x6db17  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6db1c  stloc.s  0xB
0x6db1e  ldloc.s  0xB
0x6db20  brtrue.s loc_6DB32
0x6db22  ldloc.s  6
0x6db24  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Term::get_TermSet()
0x6db29  stloc.s  0xA
0x6db2b  ldloc.s  0xA
0x6db2d  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6db32  ldloc.s  6
0x6db34  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x6db39  ldloc.3
0x6db3a  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6db3f  ldloc.s  0xB
0x6db41  brfalse.s loc_6DB5A
0x6db43  ldloc.0
0x6db44  ldloc.s  0xB
0x6db46  ldarg.s  7
0x6db48  ldc.i4.1
0x6db49  ldarg.s  9
0x6db4b  ldc.i4.1
0x6db4c  ldarg.s  8
0x6db4e  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6db53  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6db58  br.s     loc_6DBC3
0x6db5a  ldloc.0
0x6db5b  ldloc.s  0xA
0x6db5d  ldarg.s  7
0x6db5f  ldc.i4.1
0x6db60  ldarg.s  9
0x6db62  ldc.i4.1
0x6db63  ldarg.s  8
0x6db65  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6db6a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6db6f  br.s     loc_6DBC3
0x6db71  ldloc.0
0x6db72  ldloc.s  6
0x6db74  ldarg.s  7
0x6db76  ldarg.s  8
0x6db78  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetNextDisplayPageItems(class Microsoft.SharePoint.Taxonomy.Term term, int32 pageLimit, bool includeDeprecated)
0x6db7d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6db82  ldloc.s  6
0x6db84  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x6db89  ldloc.3
0x6db8a  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6db8f  br.s     loc_6DBC3
0x6db91  ldloc.s  6
0x6db93  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x6db98  ldloc.3
0x6db99  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6db9e  br.s     loc_6DBC3
0x6dba0  ldloc.0
0x6dba1  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6dba6  ldc.i4.1
0x6dba7  newarr   [mscorlib]System.Object
0x6dbac  stloc.s  0x11
0x6dbae  ldloc.s  0x11
0x6dbb0  ldc.i4.0
0x6dbb1  ldstr    aItemtype// "itemType"
0x6dbb6  stelem.ref
0x6dbb7  ldloc.s  0x11
0x6dbb9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6dbbe  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6dbc3  leave.s  loc_6DBCF
0x6dbc5  ldloc.1
0x6dbc6  brfalse.s loc_6DBCE
0x6dbc8  ldloc.1
0x6dbc9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6dbce  endfinally
0x6dbcf  leave.s  loc_6DBE2
0x6dbd1  stloc.s  0xC
0x6dbd3  ldloc.0
0x6dbd4  ldloc.s  0xC
0x6dbd6  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6dbdb  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6dbe0  leave.s  loc_6DBE2
0x6dbe2  ldloc.0
0x6dbe3  callvirt instance string Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Error()
0x6dbe8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6dbed  brfalse.s loc_6DC1A
0x6dbef  ldc.i4   0x360846
0x6dbf4  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6dbf9  ldc.i4.s 0x32
0x6dbfb  ldstr    aFeatureusageev_3// "FeatureUsageEvent: Successfully deleted"...
0x6dc00  ldc.i4.1
0x6dc01  newarr   [mscorlib]System.Object
0x6dc06  stloc.s  0x12
0x6dc08  ldloc.s  0x12
0x6dc0a  ldc.i4.0
0x6dc0b  ldarg.s  4
0x6dc0d  box      [mscorlib]System.Guid
0x6dc12  stelem.ref
0x6dc13  ldloc.s  0x12
0x6dc15  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6dc1a  ldloc.0
0x6dc1b  ret
```
