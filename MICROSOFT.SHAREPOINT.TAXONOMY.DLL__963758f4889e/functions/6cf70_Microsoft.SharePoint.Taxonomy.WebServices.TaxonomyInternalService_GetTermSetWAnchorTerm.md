# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTermSetWAnchorTerm

- ea: `0x6cf70`
- end: `0x6d0a6`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTermSetWAnchorTerm`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x4bad0`
- `0x4d510`
- `0x52350`
- `0x55050`
- `0x55610`
- `0x6cf70`
- `0x6d530`
- `0x6deb0`
- `0x706d0`
- `0x708e0`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6cf8a`: `TSMTWebServiceInvalidParam`
- `0x6cfbf`: `TSMTWebServiceInvalidParam`
- `0x6cff5`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6cf70  ldarg.2
0x6cf71  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6cf76  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6cf7b  stloc.0
0x6cf7c  ldarg.1
0x6cf7d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cf82  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6cf87  brfalse.s loc_6CFB1
0x6cf89  ldloc.0
0x6cf8a  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cf8f  ldc.i4.1
0x6cf90  newarr   [mscorlib]System.Object
0x6cf95  stloc.s  7
0x6cf97  ldloc.s  7
0x6cf99  ldc.i4.0
0x6cf9a  ldstr    aSspid// "sspId"
0x6cf9f  stelem.ref
0x6cfa0  ldloc.s  7
0x6cfa2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cfa7  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cfac  br       loc_6D0A4
0x6cfb1  ldarg.3
0x6cfb2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cfb7  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6cfbc  brfalse.s loc_6CFE6
0x6cfbe  ldloc.0
0x6cfbf  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cfc4  ldc.i4.1
0x6cfc5  newarr   [mscorlib]System.Object
0x6cfca  stloc.s  8
0x6cfcc  ldloc.s  8
0x6cfce  ldc.i4.0
0x6cfcf  ldstr    aTermsetid_1// "termSetId"
0x6cfd4  stelem.ref
0x6cfd5  ldloc.s  8
0x6cfd7  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cfdc  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cfe1  br       loc_6D0A4
0x6cfe6  ldarg.s  4
0x6cfe8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6cfed  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6cff2  brfalse.s loc_6D01C
0x6cff4  ldloc.0
0x6cff5  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cffa  ldc.i4.1
0x6cffb  newarr   [mscorlib]System.Object
0x6d000  stloc.s  9
0x6d002  ldloc.s  9
0x6d004  ldc.i4.0
0x6d005  ldstr    aAnchorid_1// "anchorId"
0x6d00a  stelem.ref
0x6d00b  ldloc.s  9
0x6d00d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d012  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d017  br       loc_6D0A4
0x6d01c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6d021  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6d026  ldc.i4.1
0x6d027  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, bool updateCache)
0x6d02c  stloc.1
0x6d02d  ldloc.1
0x6d02e  ldarg.1
0x6d02f  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6d034  stloc.2
0x6d035  ldloc.2
0x6d036  ldarg.2
0x6d037  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6d03c  ldloc.2
0x6d03d  ldarg.3
0x6d03e  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6d043  stloc.3
0x6d044  ldloc.3
0x6d045  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d04a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject>::.ctor()
0x6d04f  stloc.s  4
0x6d051  ldloc.3
0x6d052  brfalse.s loc_6D089
0x6d054  ldloc.3
0x6d055  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSetItem::get_IsAvailableForTagging()
0x6d05a  brfalse.s loc_6D089
0x6d05c  ldloc.s  4
0x6d05e  ldloc.3
0x6d05f  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x6d064  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject>::Add(var<u1>)
0x6d069  ldloc.3
0x6d06a  ldarg.s  4
0x6d06c  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSet::GetTerm(valuetype [mscorlib]System.Guid termId)
0x6d071  stloc.s  5
0x6d073  ldloc.s  5
0x6d075  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d07a  ldloc.s  4
0x6d07c  ldloc.s  5
0x6d07e  ldc.i4.0
0x6d07f  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.Term term, bool isOrphane)
0x6d084  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject>::Add(var<u1>)
0x6d089  ldloc.0
0x6d08a  ldloc.s  4
0x6d08c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d091  leave.s  loc_6D0A4
0x6d093  stloc.s  6
0x6d095  ldloc.0
0x6d096  ldloc.s  6
0x6d098  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6d09d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d0a2  leave.s  loc_6D0A4
0x6d0a4  ldloc.0
0x6d0a5  ret
```
