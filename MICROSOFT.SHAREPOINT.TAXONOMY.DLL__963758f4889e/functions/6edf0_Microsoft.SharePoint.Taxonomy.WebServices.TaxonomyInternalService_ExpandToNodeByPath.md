# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ExpandToNodeByPath

- ea: `0x6edf0`
- end: `0x6eeb6`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::ExpandToNodeByPath`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x55610`
- `0x6d530`
- `0x6de50`
- `0x6edf0`
- `0x6f060`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6ee06`: `TSMTWebServiceInvalidParam`
- `0x6ee40`: `TSMTWebServiceInvalidParam`
- `0x6ee16`: `childPathFromParent`

## pseudocode

```c

```

## disassembly

```asm
0x6edf0  ldarg.2
0x6edf1  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6edf6  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6edfb  stloc.0
0x6edfc  ldarg.s  5
0x6edfe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6ee03  brfalse.s loc_6EE2D
0x6ee05  ldloc.0
0x6ee06  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ee0b  ldc.i4.1
0x6ee0c  newarr   [mscorlib]System.Object
0x6ee11  stloc.s  4
0x6ee13  ldloc.s  4
0x6ee15  ldc.i4.0
0x6ee16  ldstr    aChildpathfromp// "childPathFromParent"
0x6ee1b  stelem.ref
0x6ee1c  ldloc.s  4
0x6ee1e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ee23  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ee28  br       loc_6EEB4
0x6ee2d  ldarg.3
0x6ee2e  ldc.i4.4
0x6ee2f  bne.un.s loc_6EE64
0x6ee31  ldarg.s  4
0x6ee33  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ee38  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ee3d  brfalse.s loc_6EE64
0x6ee3f  ldloc.0
0x6ee40  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6ee45  ldc.i4.1
0x6ee46  newarr   [mscorlib]System.Object
0x6ee4b  stloc.s  5
0x6ee4d  ldloc.s  5
0x6ee4f  ldc.i4.0
0x6ee50  ldstr    aTermsetid_1// "termSetId"
0x6ee55  stelem.ref
0x6ee56  ldloc.s  5
0x6ee58  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ee5d  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ee62  br.s     loc_6EEB4
0x6ee64  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6ee69  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6ee6e  ldarg.s  9
0x6ee70  ldarg.s  0xA
0x6ee72  ldc.i4.1
0x6ee73  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6ee78  stloc.1
0x6ee79  ldloc.1
0x6ee7a  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6ee7f  stloc.2
0x6ee80  ldloc.2
0x6ee81  ldarg.1
0x6ee82  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6ee87  stloc.3
0x6ee88  ldloc.3
0x6ee89  ldarg.2
0x6ee8a  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6ee8f  ldloc.0
0x6ee90  ldloc.3
0x6ee91  ldarg.3
0x6ee92  ldarg.s  4
0x6ee94  ldarg.s  5
0x6ee96  ldarg.s  6
0x6ee98  ldarg.s  7
0x6ee9a  ldarg.s  8
0x6ee9c  ldarg.s  0xB
0x6ee9e  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericParent> Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetSubTreeFromPath(class Microsoft.SharePoint.Taxonomy.TermStore termStore, int32 parentType, valuetype [mscorlib]System.Guid termSetId, string childPathFromParent, int32 pageLimit, bool includeDeprecated, bool includeNoneTaggableTermset, bool includeSystemGroup)
0x6eea3  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6eea8  leave.s  loc_6EEB4
0x6eeaa  ldloc.1
0x6eeab  brfalse.s loc_6EEB3
0x6eead  ldloc.1
0x6eeae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eeb3  endfinally
0x6eeb4  ldloc.0
0x6eeb5  ret
```
