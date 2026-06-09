# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ExpandToNodeById

- ea: `0x6eec0`
- end: `0x6f058`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ExpandToNodeById`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x48810`
- `0x4ba10`
- `0x4f1e0`
- `0x52350`
- `0x55050`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6eec0`
- `0x6f060`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6eedb`: `TSMTWebServiceInvalidParam`
- `0x6ef0b`: `TSMTWebServiceInvalidParam`
- `0x6ef41`: `TSMTWebServiceInvalidTermId`

## pseudocode

```c

```

## disassembly

```asm
0x6eec0  ldarg.s  0xB
0x6eec2  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6eec7  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6eecc  stloc.0
0x6eecd  ldarg.1
0x6eece  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6eed3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6eed8  brfalse.s loc_6EEFD
0x6eeda  ldloc.0
0x6eedb  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6eee0  ldc.i4.1
0x6eee1  newarr   [mscorlib]System.Object
0x6eee6  stloc.s  8
0x6eee8  ldloc.s  8
0x6eeea  ldc.i4.0
0x6eeeb  ldstr    aSspid// "sspId"
0x6eef0  stelem.ref
0x6eef1  ldloc.s  8
0x6eef3  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6eef8  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6eefd  ldarg.3
0x6eefe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ef03  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ef08  brfalse.s loc_6EF32
0x6ef0a  ldloc.0
0x6ef0b  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ef10  ldc.i4.1
0x6ef11  newarr   [mscorlib]System.Object
0x6ef16  stloc.s  9
0x6ef18  ldloc.s  9
0x6ef1a  ldc.i4.0
0x6ef1b  ldstr    aTermsetid_1// "termSetId"
0x6ef20  stelem.ref
0x6ef21  ldloc.s  9
0x6ef23  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ef28  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ef2d  br       loc_6F056
0x6ef32  ldarg.s  5
0x6ef34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ef39  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ef3e  brfalse.s loc_6EF5B
0x6ef40  ldloc.0
0x6ef41  ldstr    aTsmtwebservice_0// "TSMTWebServiceInvalidTermId"
0x6ef46  ldc.i4.0
0x6ef47  newarr   [mscorlib]System.Object
0x6ef4c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ef51  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ef56  br       loc_6F056
0x6ef5b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6ef60  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6ef65  ldarg.s  9
0x6ef67  ldarg.s  0xA
0x6ef69  ldc.i4.1
0x6ef6a  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6ef6f  stloc.1
0x6ef70  ldloc.1
0x6ef71  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6ef76  stloc.2
0x6ef77  ldloc.2
0x6ef78  ldarg.1
0x6ef79  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6ef7e  stloc.3
0x6ef7f  ldloc.3
0x6ef80  ldarg.s  0xB
0x6ef82  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6ef87  ldloc.3
0x6ef88  ldarg.3
0x6ef89  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6ef8e  stloc.s  4
0x6ef90  ldloc.s  4
0x6ef92  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6ef97  ldnull
0x6ef98  stloc.s  5
0x6ef9a  ldarg.2
0x6ef9b  ldc.i4.4
0x6ef9c  bne.un.s loc_6EFB0
0x6ef9e  ldloc.s  4
0x6efa0  ldarg.s  4
0x6efa2  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSet::GetTerm(valuetype [mscorlib]System.Guid termId)
0x6efa7  stloc.s  5
0x6efa9  ldloc.s  4
0x6efab  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6efb0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6efb5  stloc.s  6
0x6efb7  ldloc.s  4
0x6efb9  ldarg.s  5
0x6efbb  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSet::GetTerm(valuetype [mscorlib]System.Guid termId)
0x6efc0  stloc.s  7
0x6efc2  ldloc.s  7
0x6efc4  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6efc9  br.s     loc_6EFFE
0x6efcb  ldloc.s  6
0x6efcd  ldc.i4.0
0x6efce  ldloc.s  7
0x6efd0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x6efd5  stloc.s  0xA
0x6efd7  ldloca.s 0xA
0x6efd9  constrained. [mscorlib]System.Guid
0x6efdf  callvirt instance string [mscorlib]System.Object::ToString()
0x6efe4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x6efe9  pop
0x6efea  ldloc.s  6
0x6efec  ldc.i4.0
0x6efed  ldc.i4.s 0x7C
0x6efef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, char)
0x6eff4  pop
0x6eff5  ldloc.s  7
0x6eff7  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.Term::get_Parent()
0x6effc  stloc.s  7
0x6effe  ldloc.s  7
0x6f000  brfalse.s loc_6F008
0x6f002  ldloc.s  7
0x6f004  ldloc.s  5
0x6f006  bne.un.s loc_6EFCB
0x6f008  ldloc.s  7
0x6f00a  brtrue.s loc_6F01D
0x6f00c  ldloc.s  6
0x6f00e  ldc.i4.0
0x6f00f  ldarg.3
0x6f010  box      [mscorlib]System.Guid
0x6f015  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, object)
0x6f01a  pop
0x6f01b  br.s     loc_6F02D
0x6f01d  ldloc.s  6
0x6f01f  ldc.i4.0
0x6f020  ldarg.s  4
0x6f022  box      [mscorlib]System.Guid
0x6f027  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, object)
0x6f02c  pop
0x6f02d  ldloc.0
0x6f02e  ldloc.3
0x6f02f  ldarg.2
0x6f030  ldarg.3
0x6f031  ldloc.s  6
0x6f033  callvirt instance string [mscorlib]System.Object::ToString()
0x6f038  ldarg.s  6
0x6f03a  ldarg.s  7
0x6f03c  ldarg.s  8
0x6f03e  ldarg.s  0xC
0x6f040  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSubTreeFromPath(class Microsoft.SharePoint.Taxonomy.TermStore termStore, int32 parentType, valuetype [mscorlib]System.Guid termSetId, string childPathFromParent, int32 pageLimit, bool includeDeprecated, bool includeNoneTaggableTermset, bool includeSystemGroup)
0x6f045  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6f04a  leave.s  loc_6F056
0x6f04c  ldloc.1
0x6f04d  brfalse.s loc_6F055
0x6f04f  ldloc.1
0x6f050  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f055  endfinally
0x6f056  ldloc.0
0x6f057  ret
```
