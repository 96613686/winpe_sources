# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetChildTermsInTermWithPaging

- ea: `0x6dd60`
- end: `0x6de49`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetChildTermsInTermWithPaging`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x54710`
- `0x55610`
- `0x6d530`
- `0x6dd60`
- `0x6de50`
- `0x6deb0`
- `0x6fa50`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6dd7a`: `TSMTWebServiceInvalidParam`
- `0x6ddb0`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6dd60  ldarg.2
0x6dd61  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6dd66  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6dd6b  stloc.0
0x6dd6c  ldarg.3
0x6dd6d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6dd72  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6dd77  brfalse.s loc_6DDA1
0x6dd79  ldloc.0
0x6dd7a  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6dd7f  ldc.i4.1
0x6dd80  newarr   [mscorlib]System.Object
0x6dd85  stloc.s  6
0x6dd87  ldloc.s  6
0x6dd89  ldc.i4.0
0x6dd8a  ldstr    aGuid// "guid"
0x6dd8f  stelem.ref
0x6dd90  ldloc.s  6
0x6dd92  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6dd97  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6dd9c  br       loc_6DE47
0x6dda1  ldarg.s  4
0x6dda3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6dda8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ddad  brfalse.s loc_6DDD4
0x6ddaf  ldloc.0
0x6ddb0  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ddb5  ldc.i4.1
0x6ddb6  newarr   [mscorlib]System.Object
0x6ddbb  stloc.s  7
0x6ddbd  ldloc.s  7
0x6ddbf  ldc.i4.0
0x6ddc0  ldstr    aTermsetid_3// "termsetId"
0x6ddc5  stelem.ref
0x6ddc6  ldloc.s  7
0x6ddc8  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ddcd  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ddd2  br.s     loc_6DE47
0x6ddd4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6ddd9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6ddde  ldarg.s  0xA
0x6dde0  ldarg.s  0xB
0x6dde2  ldc.i4.1
0x6dde3  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6dde8  stloc.1
0x6dde9  ldloc.1
0x6ddea  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6ddef  stloc.2
0x6ddf0  ldloc.2
0x6ddf1  ldarg.1
0x6ddf2  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6ddf7  stloc.3
0x6ddf8  ldloc.3
0x6ddf9  ldarg.2
0x6ddfa  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6ddff  ldloc.3
0x6de00  ldarg.s  4
0x6de02  ldarg.3
0x6de03  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6de08  stloc.s  4
0x6de0a  ldloc.s  4
0x6de0c  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6de11  ldloc.0
0x6de12  ldloc.s  4
0x6de14  ldarg.s  6
0x6de16  ldarg.s  8
0x6de18  ldarg.s  9
0x6de1a  ldarg.s  7
0x6de1c  ldarg.s  5
0x6de1e  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTerms(class Microsoft.SharePoint.Taxonomy.TermSetItem termSetItem, int32 pageLimit, bool includeCurrentChild, valuetype [mscorlib]System.Guid currentChildGuid, bool pagingForward, bool includeDeprecated)
0x6de23  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6de28  leave.s  loc_6DE34
0x6de2a  ldloc.1
0x6de2b  brfalse.s loc_6DE33
0x6de2d  ldloc.1
0x6de2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6de33  endfinally
0x6de34  leave.s  loc_6DE47
0x6de36  stloc.s  5
0x6de38  ldloc.0
0x6de39  ldloc.s  5
0x6de3b  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6de40  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6de45  leave.s  loc_6DE47
0x6de47  ldloc.0
0x6de48  ret
```
