# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::PickTermSets

- ea: `0x6cdb0`
- end: `0x6cf64`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::PickTermSets`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x81c0`
- `0x2ad40`
- `0x4ba10`
- `0x4d510`
- `0x55050`
- `0x6bba0`
- `0x6cdb0`
- `0x6d530`
- `0x6de50`
- `0x6deb0`
- `0x706e0`
- `0x71170`
- `0x71190`
- `0x71200`

## string_xrefs

- `0x6cdc6`: `TSMTWebServiceInvalidParam`
- `0x6cdf6`: `TSMTWebServiceInvalidParam`

## pseudocode

```c

```

## disassembly

```asm
0x6cdb0  ldarg.s  5
0x6cdb2  call     void Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::SetThreadLcid(int32 lcid)
0x6cdb7  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6cdbc  stloc.0
0x6cdbd  ldarg.1
0x6cdbe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6cdc3  brfalse.s loc_6CDED
0x6cdc5  ldloc.0
0x6cdc6  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cdcb  ldc.i4.1
0x6cdcc  newarr   [mscorlib]System.Object
0x6cdd1  stloc.s  0xB
0x6cdd3  ldloc.s  0xB
0x6cdd5  ldc.i4.0
0x6cdd6  ldstr    aSspids// "sspIds"
0x6cddb  stelem.ref
0x6cddc  ldloc.s  0xB
0x6cdde  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cde3  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cde8  br       loc_6CF62
0x6cded  ldarg.2
0x6cdee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6cdf3  brfalse.s loc_6CE1D
0x6cdf5  ldloc.0
0x6cdf6  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6cdfb  ldc.i4.1
0x6cdfc  newarr   [mscorlib]System.Object
0x6ce01  stloc.s  0xC
0x6ce03  ldloc.s  0xC
0x6ce05  ldc.i4.0
0x6ce06  ldstr    aTermsetguids// "termsetGuids"
0x6ce0b  stelem.ref
0x6ce0c  ldloc.s  0xC
0x6ce0e  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ce13  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ce18  br       loc_6CF62
0x6ce1d  ldarg.1
0x6ce1e  ldc.i4.1
0x6ce1f  newarr   [mscorlib]System.Char
0x6ce24  stloc.s  0xD
0x6ce26  ldloc.s  0xD
0x6ce28  ldc.i4.0
0x6ce29  ldc.i4.s 0x3B
0x6ce2b  stelem.i2
0x6ce2c  ldloc.s  0xD
0x6ce2e  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6ce33  stloc.1
0x6ce34  ldarg.2
0x6ce35  ldc.i4.1
0x6ce36  newarr   [mscorlib]System.Char
0x6ce3b  stloc.s  0xE
0x6ce3d  ldloc.s  0xE
0x6ce3f  ldc.i4.0
0x6ce40  ldc.i4.s 0x3B
0x6ce42  stelem.i2
0x6ce43  ldloc.s  0xE
0x6ce45  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6ce4a  stloc.2
0x6ce4b  ldloc.1
0x6ce4c  ldlen
0x6ce4d  conv.i4
0x6ce4e  ldloc.2
0x6ce4f  ldlen
0x6ce50  conv.i4
0x6ce51  beq.s    loc_6CE78
0x6ce53  ldloc.0
0x6ce54  ldstr    aTermsetidinval// "TermSetIdInvalid"
0x6ce59  ldc.i4.1
0x6ce5a  newarr   [mscorlib]System.Object
0x6ce5f  stloc.s  0xF
0x6ce61  ldloc.s  0xF
0x6ce63  ldc.i4.0
0x6ce64  ldstr    aTermsetguids// "termsetGuids"
0x6ce69  stelem.ref
0x6ce6a  ldloc.s  0xF
0x6ce6c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6ce71  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6ce76  ldloc.0
0x6ce77  ret
0x6ce78  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x6ce7d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x6ce82  ldarg.3
0x6ce83  ldarg.s  4
0x6ce85  ldc.i4.1
0x6ce86  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x6ce8b  stloc.3
0x6ce8c  ldloc.3
0x6ce8d  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x6ce92  stloc.s  4
0x6ce94  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject>::.ctor()
0x6ce99  stloc.s  5
0x6ce9b  ldc.i4.0
0x6ce9c  stloc.s  6
0x6ce9e  br       loc_6CF31
0x6cea3  ldloc.s  4
0x6cea5  ldloc.1
0x6cea6  ldloc.s  6
0x6cea8  ldelem.ref
0x6cea9  callvirt instance string [mscorlib]System.String::Trim()
0x6ceae  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6ceb3  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6ceb8  stloc.s  7
0x6ceba  ldloca.s 8
0x6cebc  ldloc.2
0x6cebd  ldloc.s  6
0x6cebf  ldelem.ref
0x6cec0  callvirt instance string [mscorlib]System.String::Trim()
0x6cec5  call     instance void [mscorlib]System.Guid::.ctor(string)
0x6ceca  ldloc.s  8
0x6cecc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ced1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ced6  brfalse.s loc_6CF2B
0x6ced8  ldloc.s  7
0x6ceda  ldloc.s  8
0x6cedc  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6cee1  stloc.s  9
0x6cee3  ldloc.s  9
0x6cee5  brtrue.s loc_6CF0A
0x6cee7  ldstr    aTermsetidinval// "TermSetIdInvalid"
0x6ceec  ldc.i4.1
0x6ceed  newarr   [mscorlib]System.Object
0x6cef2  stloc.s  0x10
0x6cef4  ldloc.s  0x10
0x6cef6  ldc.i4.0
0x6cef7  ldstr    aTermsetguids// "termsetGuids"
0x6cefc  stelem.ref
0x6cefd  ldloc.s  0x10
0x6ceff  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6cf04  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6cf09  throw
0x6cf0a  ldloc.s  9
0x6cf0c  callvirt instance bool Microsoft.SharePoint.Taxonomy.TermSetItem::get_IsAvailableForTagging()
0x6cf11  brtrue.s loc_6CF1C
0x6cf13  ldloc.s  9
0x6cf15  call     bool Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::IsSpecialCaseForNavigationTermSet(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x6cf1a  brfalse.s loc_6CF2B
0x6cf1c  ldloc.s  5
0x6cf1e  ldloc.s  9
0x6cf20  ldc.i4.1
0x6cf21  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.TermSet termSet, bool includeLanguages)
0x6cf26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject>::Add(var<u1>)
0x6cf2b  ldloc.s  6
0x6cf2d  ldc.i4.1
0x6cf2e  add.ovf
0x6cf2f  stloc.s  6
0x6cf31  ldloc.s  6
0x6cf33  ldloc.2
0x6cf34  ldlen
0x6cf35  conv.i4
0x6cf36  blt      loc_6CEA3
0x6cf3b  ldloc.0
0x6cf3c  ldloc.s  5
0x6cf3e  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6cf43  leave.s  loc_6CF4F
0x6cf45  ldloc.3
0x6cf46  brfalse.s loc_6CF4E
0x6cf48  ldloc.3
0x6cf49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cf4e  endfinally
0x6cf4f  leave.s  loc_6CF62
0x6cf51  stloc.s  0xA
0x6cf53  ldloc.0
0x6cf54  ldloc.s  0xA
0x6cf56  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6cf5b  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6cf60  leave.s  loc_6CF62
0x6cf62  ldloc.0
0x6cf63  ret
```
