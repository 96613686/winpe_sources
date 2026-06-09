# Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::CreateTaxonomyItem

- ea: `0x6d560`
- end: `0x6d895`
- name: `Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::CreateTaxonomyItem`
- size: `821`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d450`
- `0x6d8a0`

## callees

- `0x81b0`
- `0x81c0`
- `0x2ad40`
- `0x48e90`
- `0x4d190`
- `0x50620`
- `0x53f80`
- `0x54090`
- `0x545b0`
- `0x54710`
- `0x55050`
- `0x55440`
- `0x55610`
- `0x56720`
- `0x6d560`
- `0x6deb0`
- `0x6df30`
- `0x70460`
- `0x706d0`
- `0x708e0`
- `0x70fe0`
- `0x71170`
- `0x71180`
- `0x71190`
- `0x711d0`
- `0x71200`

## string_xrefs

- `0x6d581`: `TSMTWebServiceInvalidParam`
- `0x6d5b4`: `TSMTWebServiceInvalidParam`
- `0x6d5ee`: `TSMTWebServiceInvalidParam`
- `0x6d61f`: `TSMTWebServiceInvalidParam`
- `0x6d64b`: `TSMTWebServiceInvalidParam`
- `0x6d7f7`: `TSMTWebServiceInvalidParam`
- `0x6d884`: `" was succesfully created.`

## pseudocode

```c

```

## disassembly

```asm
0x6d560  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::.ctor()
0x6d565  stloc.0
0x6d566  ldarg.s  5
0x6d568  brfalse.s loc_6D573
0x6d56a  ldarg.s  5
0x6d56c  callvirt instance string [mscorlib]System.String::Trim()
0x6d571  starg.s  5
0x6d573  ldarg.0
0x6d574  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d579  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d57e  brfalse.s loc_6D5A3
0x6d580  ldloc.0
0x6d581  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d586  ldc.i4.1
0x6d587  newarr   [mscorlib]System.Object
0x6d58c  stloc.s  0xF
0x6d58e  ldloc.s  0xF
0x6d590  ldc.i4.0
0x6d591  ldstr    aSspid// "sspId"
0x6d596  stelem.ref
0x6d597  ldloc.s  0xF
0x6d599  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d59e  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d5a3  ldarg.3
0x6d5a4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d5a9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d5ae  brfalse.s loc_6D5DB
0x6d5b0  ldarg.2
0x6d5b1  brfalse.s loc_6D5DB
0x6d5b3  ldloc.0
0x6d5b4  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d5b9  ldc.i4.1
0x6d5ba  newarr   [mscorlib]System.Object
0x6d5bf  stloc.s  0x10
0x6d5c1  ldloc.s  0x10
0x6d5c3  ldc.i4.0
0x6d5c4  ldstr    aParentid_0// "parentId"
0x6d5c9  stelem.ref
0x6d5ca  ldloc.s  0x10
0x6d5cc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d5d1  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d5d6  br       loc_6D856
0x6d5db  ldarg.2
0x6d5dc  ldc.i4.4
0x6d5dd  bne.un.s loc_6D615
0x6d5df  ldarg.s  4
0x6d5e1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6d5e6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6d5eb  brfalse.s loc_6D615
0x6d5ed  ldloc.0
0x6d5ee  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d5f3  ldc.i4.1
0x6d5f4  newarr   [mscorlib]System.Object
0x6d5f9  stloc.s  0x11
0x6d5fb  ldloc.s  0x11
0x6d5fd  ldc.i4.0
0x6d5fe  ldstr    aTermsetid_3// "termsetId"
0x6d603  stelem.ref
0x6d604  ldloc.s  0x11
0x6d606  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d60b  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d610  br       loc_6D856
0x6d615  ldarg.s  5
0x6d617  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6d61c  brfalse.s loc_6D646
0x6d61e  ldloc.0
0x6d61f  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d624  ldc.i4.1
0x6d625  newarr   [mscorlib]System.Object
0x6d62a  stloc.s  0x12
0x6d62c  ldloc.s  0x12
0x6d62e  ldc.i4.0
0x6d62f  ldstr    aNewname// "newName"
0x6d634  stelem.ref
0x6d635  ldloc.s  0x12
0x6d637  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d63c  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d641  br       loc_6D856
0x6d646  ldarg.s  6
0x6d648  brtrue.s loc_6D672
0x6d64a  ldloc.0
0x6d64b  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d650  ldc.i4.1
0x6d651  newarr   [mscorlib]System.Object
0x6d656  stloc.s  0x13
0x6d658  ldloc.s  0x13
0x6d65a  ldc.i4.0
0x6d65b  ldstr    aTaxsession// "taxSession"
0x6d660  stelem.ref
0x6d661  ldloc.s  0x13
0x6d663  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d668  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d66d  br       loc_6D856
0x6d672  ldarg.s  6
0x6d674  ldarg.0
0x6d675  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::GetTermStore(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, valuetype [mscorlib]System.Guid sspId)
0x6d67a  stloc.1
0x6d67b  ldloc.1
0x6d67c  ldarg.1
0x6d67d  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ValidateLanguage(int32 lcid)
0x6d682  leave.s  loc_6D6B1
0x6d684  stloc.2
0x6d685  ldc.i4   0x66373164
0x6d68a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6d68f  ldc.i4.s 0x64
0x6d691  ldloc.2
0x6d692  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d697  ldloc.2
0x6d698  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x6d69d  call     string [mscorlib]System.String::Concat(string, string)
0x6d6a2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6d6a7  ldloc.1
0x6d6a8  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_DefaultLanguage()
0x6d6ad  starg.s  1
0x6d6af  leave.s  loc_6D6B1
0x6d6b1  ldloc.1
0x6d6b2  ldarg.1
0x6d6b3  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::set_WorkingLanguage(int32 value)
0x6d6b8  ldarg.2
0x6d6b9  brtrue.s loc_6D6DB
0x6d6bb  ldloc.1
0x6d6bc  ldarg.s  5
0x6d6be  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::CreateGroup(string name)
0x6d6c3  stloc.3
0x6d6c4  ldloc.1
0x6d6c5  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d6ca  ldloc.0
0x6d6cb  ldloc.3
0x6d6cc  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.Group group)
0x6d6d1  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d6d6  br       loc_6D819
0x6d6db  ldarg.2
0x6d6dc  ldc.i4.1
0x6d6dd  bne.un.s loc_6D712
0x6d6df  ldloc.1
0x6d6e0  ldarg.3
0x6d6e1  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::GetGroup(valuetype [mscorlib]System.Guid id)
0x6d6e6  stloc.s  4
0x6d6e8  ldloc.s  4
0x6d6ea  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d6ef  ldloc.s  4
0x6d6f1  ldarg.s  5
0x6d6f3  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.Group::CreateTermSet(string name)
0x6d6f8  stloc.s  5
0x6d6fa  ldloc.1
0x6d6fb  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d700  ldloc.0
0x6d701  ldloc.s  5
0x6d703  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.TermSet termSet)
0x6d708  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d70d  br       loc_6D819
0x6d712  ldarg.2
0x6d713  ldc.i4.3
0x6d714  beq.s    loc_6D71F
0x6d716  ldarg.2
0x6d717  ldc.i4.s 0xC
0x6d719  beq.s    loc_6D71F
0x6d71b  ldarg.2
0x6d71c  ldc.i4.6
0x6d71d  bne.un.s loc_6D754
0x6d71f  ldloc.1
0x6d720  ldarg.3
0x6d721  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x6d726  stloc.s  6
0x6d728  ldloc.s  6
0x6d72a  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d72f  ldloc.s  6
0x6d731  ldarg.s  5
0x6d733  ldarg.1
0x6d734  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x6d739  stloc.s  7
0x6d73b  ldloc.1
0x6d73c  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d741  ldloc.0
0x6d742  ldloc.s  7
0x6d744  ldc.i4.0
0x6d745  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.Term term, bool isOrphane)
0x6d74a  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d74f  br       loc_6D819
0x6d754  ldarg.2
0x6d755  ldc.i4.4
0x6d756  bne.un   loc_6D7F6
0x6d75b  ldloc.1
0x6d75c  ldarg.s  4
0x6d75e  ldarg.3
0x6d75f  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermStore::GetTerm(valuetype [mscorlib]System.Guid termSetId, valuetype [mscorlib]System.Guid termId)
0x6d764  stloc.s  8
0x6d766  ldloc.s  8
0x6d768  call     void Microsoft.SharePoint.Taxonomy.OM.CodeBehind.TermStoreManager::IfNullRaiseStoreChangeExp(object item)
0x6d76d  ldloc.s  8
0x6d76f  ldarg.s  5
0x6d771  ldarg.1
0x6d772  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x6d777  stloc.s  9
0x6d779  ldloc.1
0x6d77a  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x6d77f  ldloc.0
0x6d780  ldloc.s  9
0x6d782  ldc.i4.0
0x6d783  newobj   instance void Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::.ctor(class Microsoft.SharePoint.Taxonomy.Term term, bool isOrphane)
0x6d788  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Content(object value)
0x6d78d  ldloc.s  8
0x6d78f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term> Microsoft.SharePoint.Taxonomy.Term::get_ReusedPinnedTerms()
0x6d794  stloc.s  0xA
0x6d796  ldloc.s  0xA
0x6d798  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Count()
0x6d79d  ldc.i4.0
0x6d79e  ble.s    loc_6D819
0x6d7a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6d7a5  stloc.s  0xB
0x6d7a7  ldloc.s  0xA
0x6d7a9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x6d7ae  stloc.s  0x14
0x6d7b0  br.s     loc_6D7C9
0x6d7b2  ldloca.s 0x14
0x6d7b4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x6d7b9  stloc.s  0xC
0x6d7bb  ldloc.s  0xB
0x6d7bd  ldloc.s  0xC
0x6d7bf  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::BuildTermPath(class Microsoft.SharePoint.Taxonomy.Term term)
0x6d7c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6d7c9  ldloca.s 0x14
0x6d7cb  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>::MoveNext()
0x6d7d0  brtrue.s loc_6D7B2
0x6d7d2  leave.s  loc_6D7E2
0x6d7d4  ldloca.s 0x14
0x6d7d6  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Term>
0x6d7dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d7e1  endfinally
0x6d7e2  ldloc.s  0xB
0x6d7e4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x6d7e9  ldc.i4.0
0x6d7ea  ble.s    loc_6D819
0x6d7ec  ldloc.0
0x6d7ed  ldloc.s  0xB
0x6d7ef  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_PinData(object value)
0x6d7f4  br.s     loc_6D819
0x6d7f6  ldloc.0
0x6d7f7  ldstr    aTsmtwebservice// "TSMTWebServiceInvalidParam"
0x6d7fc  ldc.i4.1
0x6d7fd  newarr   [mscorlib]System.Object
0x6d802  stloc.s  0x15
0x6d804  ldloc.s  0x15
0x6d806  ldc.i4.0
0x6d807  ldstr    aParenttype// "parentType"
0x6d80c  stelem.ref
0x6d80d  ldloc.s  0x15
0x6d80f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x6d814  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d819  leave.s  loc_6D856
0x6d81b  stloc.s  0xD
0x6d81d  ldloc.s  0xD
0x6d81f  isinst   [mscorlib]System.ArgumentException
0x6d824  brfalse.s loc_6D847
0x6d826  ldloc.s  0xD
0x6d828  isinst   [mscorlib]System.ArgumentNullException
0x6d82d  brtrue.s loc_6D847
0x6d82f  ldloc.s  0xD
0x6d831  isinst   [mscorlib]System.ArgumentOutOfRangeException
0x6d836  brtrue.s loc_6D847
0x6d838  ldloc.0
0x6d839  ldloc.s  0xD
0x6d83b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6d840  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d845  br.s     loc_6D854
0x6d847  ldloc.0
0x6d848  ldloc.s  0xD
0x6d84a  call     string Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::HandleException(class [mscorlib]System.Exception exp)
0x6d84f  callvirt instance void Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::set_Error(string value)
0x6d854  leave.s  loc_6D856
0x6d856  ldloc.0
0x6d857  callvirt instance object Microsoft.SharePoint.Taxonomy.WebServices.TSMTReturnObject::get_Content()
0x6d85c  isinst   Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject
0x6d861  stloc.s  0xE
0x6d863  ldloc.s  0xE
0x6d865  brfalse.s loc_6D893
0x6d867  ldc.i4   0x360845
0x6d86c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x6d871  ldc.i4.s 0x32
0x6d873  ldstr    aFeatureusageev_2// "FeatureUsageEvent: Term store item of t"...
0x6d878  ldloc.s  0xE
0x6d87a  callvirt instance int32 Microsoft.SharePoint.Taxonomy.WebServices.TermStoreGenericObject::get_Tp()
0x6d87f  box      [mscorlib]System.Int32
0x6d884  ldstr    aWasSuccesfully// "\" was succesfully created."
0x6d889  call     string [mscorlib]System.String::Concat(object, object, object)
0x6d88e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x6d893  ldloc.0
0x6d894  ret
```
