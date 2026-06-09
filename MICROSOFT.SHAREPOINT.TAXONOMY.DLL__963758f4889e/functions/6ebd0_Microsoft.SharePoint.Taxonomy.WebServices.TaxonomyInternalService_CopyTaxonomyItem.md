# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::CopyTaxonomyItem

- ea: `0x6ebd0`
- end: `0x6ed6a`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::CopyTaxonomyItem`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x4de70`
- `0x51c20`
- `0x53f80`
- `0x54710`
- `0x55050`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x6ebd0`
- `0x6ed70`
- `0x706d0`
- `0x708e0`
- `0x71160`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6ebeb`: `TSMTWebServiceInvalidParam`
- `0x6ec25`: `TSMTWebServiceInvalidParam`
- `0x6ecef`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6ebd0  ldarg.2
0x6ebd1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6ebd6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6ebdb  stloc.0
0x6ebdc  ldarg.s  4
0x6ebde  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ebe3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ebe8  brfalse.s loc_6EC12
0x6ebea  ldloc.0
0x6ebeb  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ebf0  ldc.i4.1
0x6ebf1  newarr   [mscorlib]System.Object
0x6ebf6  stloc.s  9
0x6ebf8  ldloc.s  9
0x6ebfa  ldc.i4.0
0x6ebfb  ldstr    aItemid// "itemId"
0x6ec00  stelem.ref
0x6ec01  ldloc.s  9
0x6ec03  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ec08  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ec0d  br       loc_6ED30
0x6ec12  ldarg.3
0x6ec13  ldc.i4.4
0x6ec14  bne.un.s loc_6EC4C
0x6ec16  ldarg.s  5
0x6ec18  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ec1d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ec22  brfalse.s loc_6EC4C
0x6ec24  ldloc.0
0x6ec25  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ec2a  ldc.i4.1
0x6ec2b  newarr   [mscorlib]System.Object
0x6ec30  stloc.s  0xA
0x6ec32  ldloc.s  0xA
0x6ec34  ldc.i4.0
0x6ec35  ldstr    aTermsetid_3// "termsetId"
0x6ec3a  stelem.ref
0x6ec3b  ldloc.s  0xA
0x6ec3d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ec42  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ec47  br       loc_6ED30
0x6ec4c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6ec51  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6ec56  ldarg.s  7
0x6ec58  ldarg.s  8
0x6ec5a  ldc.i4.1
0x6ec5b  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6ec60  stloc.1
0x6ec61  ldloc.1
0x6ec62  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6ec67  stloc.2
0x6ec68  ldloc.2
0x6ec69  ldarg.1
0x6ec6a  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6ec6f  stloc.3
0x6ec70  ldloc.3
0x6ec71  ldarg.2
0x6ec72  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6ec77  ldarg.3
0x6ec78  ldc.i4.4
0x6ec79  beq.s    loc_6EC7F
0x6ec7b  ldarg.3
0x6ec7c  ldc.i4.7
0x6ec7d  bne.un.s loc_6ECBB
0x6ec7f  ldloc.3
0x6ec80  ldarg.s  5
0x6ec82  ldarg.s  4
0x6ec84  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6ec89  stloc.s  4
0x6ec8b  ldloc.s  4
0x6ec8d  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6ec92  ldloc.s  4
0x6ec94  ldarg.s  6
0x6ec96  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::Copy(bool doCopyChildren)
0x6ec9b  stloc.s  5
0x6ec9d  ldloc.3
0x6ec9e  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6eca3  ldloc.0
0x6eca4  ldloc.s  5
0x6eca6  ldc.i4.0
0x6eca7  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.Term term, bool isOrphane)
0x6ecac  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6ecb1  ldloc.0
0x6ecb2  ldloc.s  4
0x6ecb4  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GeneratePinData(class Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject returnVal, class Microsoft.SharePoint.Taxonomy.Term term)
0x6ecb9  br.s     loc_6ED11
0x6ecbb  ldarg.3
0x6ecbc  ldc.i4.3
0x6ecbd  bne.un.s loc_6ECEE
0x6ecbf  ldloc.3
0x6ecc0  ldarg.s  4
0x6ecc2  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6ecc7  stloc.s  6
0x6ecc9  ldloc.s  6
0x6eccb  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6ecd0  ldloc.s  6
0x6ecd2  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermSet::Copy()
0x6ecd7  stloc.s  7
0x6ecd9  ldloc.3
0x6ecda  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6ecdf  ldloc.0
0x6ece0  ldloc.s  7
0x6ece2  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x6ece7  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6ecec  br.s     loc_6ED11
0x6ecee  ldloc.0
0x6ecef  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ecf4  ldc.i4.1
0x6ecf5  newarr   [mscorlib]System.Object
0x6ecfa  stloc.s  0xB
0x6ecfc  ldloc.s  0xB
0x6ecfe  ldc.i4.0
0x6ecff  ldstr    aItemtype// "itemType"
0x6ed04  stelem.ref
0x6ed05  ldloc.s  0xB
0x6ed07  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ed0c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ed11  leave.s  loc_6ED1D
0x6ed13  ldloc.1
0x6ed14  brfalse.s loc_6ED1C
0x6ed16  ldloc.1
0x6ed17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ed1c  endfinally
0x6ed1d  leave.s  loc_6ED30
0x6ed1f  stloc.s  8
0x6ed21  ldloc.0
0x6ed22  ldloc.s  8
0x6ed24  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6ed29  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ed2e  leave.s  loc_6ED30
0x6ed30  ldloc.0
0x6ed31  callvirt instance string Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Error()
0x6ed36  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6ed3b  brfalse.s loc_6ED68
0x6ed3d  ldc.i4   0x36084B
0x6ed42  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6ed47  ldc.i4.s 0x32
0x6ed49  ldstr    aFeatureusageev_8// "FeatureUsageEvent: Successfully copied "...
0x6ed4e  ldc.i4.1
0x6ed4f  newarr   [mscorlib]System.Object
0x6ed54  stloc.s  0xC
0x6ed56  ldloc.s  0xC
0x6ed58  ldc.i4.0
0x6ed59  ldarg.s  4
0x6ed5b  box      [mscorlib]System.Guid
0x6ed60  stelem.ref
0x6ed61  ldloc.s  0xC
0x6ed63  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x6ed68  ldloc.0
0x6ed69  ret
```
