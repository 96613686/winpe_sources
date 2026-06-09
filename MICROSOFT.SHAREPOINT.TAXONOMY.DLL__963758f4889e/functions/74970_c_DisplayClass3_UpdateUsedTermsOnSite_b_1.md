# <>c__DisplayClass3::<UpdateUsedTermsOnSite>b__1

- ea: `0x74970`
- end: `0x74ab5`
- name: `<>c__DisplayClass3::<UpdateUsedTermsOnSite>b__1`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x55560`
- `0x55c60`
- `0x74970`

## string_xrefs

- `0x74a16`: `UpdateUsedTermsOnSite Encountered an item with no TermStoreId set.  Skipping over to next term.`
- `0x74a2f`: `UpdateUsedTermsOnSite stopped due to null reference exception.  Skipping over to next term.`
- `0x74aa8`: `UpdateUsedTermsOnSite stopped due to null reference exception.`

## pseudocode

```c

```

## disassembly

```asm
0x74970  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x74975  stloc.0
0x74976  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x7497b  stloc.1
0x7497c  ldc.i4.0
0x7497d  stloc.2
0x7497e  ldarg.1
0x7497f  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x74984  stloc.s  5
0x74986  br       loc_74A3B
0x7498b  ldloc.s  5
0x7498d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x74992  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x74997  stloc.3
0x74998  ldloc.3
0x74999  ldstr    aIdfortermstore// "IdForTermStore"
0x7499e  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x749a3  brfalse.s loc_74A0A
0x749a5  ldloca.s 4
0x749a7  ldloc.3
0x749a8  ldstr    aIdfortermstore// "IdForTermStore"
0x749ad  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x749b2  callvirt instance string [mscorlib]System.Object::ToString()
0x749b7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x749bc  ldloc.s  4
0x749be  ldarg.0
0x749bf  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore <>c__DisplayClass3::<>4__this
0x749c4  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_Id()
0x749c9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x749ce  brfalse.s loc_74A20
0x749d0  ldloc.1
0x749d1  ldloc.3
0x749d2  ldstr    aIdforterm// "IdForTerm"
0x749d7  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x749dc  callvirt instance string [mscorlib]System.Object::ToString()
0x749e1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x749e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x749eb  ldloc.0
0x749ec  ldloc.3
0x749ed  ldstr    aIdfortermset// "IdForTermSet"
0x749f2  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItem::get_Item(string)
0x749f7  callvirt instance string [mscorlib]System.Object::ToString()
0x749fc  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x74a01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x74a06  ldc.i4.1
0x74a07  stloc.2
0x74a08  br.s     loc_74A20
0x74a0a  ldc.i4   0x67316D74
0x74a0f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x74a14  ldc.i4.s 0x32
0x74a16  ldstr    aUpdateusedterm// "UpdateUsedTermsOnSite Encountered an it"...
0x74a1b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x74a20  leave.s  loc_74A3B
0x74a22  pop
0x74a23  ldc.i4   0x67316D75
0x74a28  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x74a2d  ldc.i4.s 0xA
0x74a2f  ldstr    aUpdateusedterm_0// "UpdateUsedTermsOnSite stopped due to nu"...
0x74a34  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x74a39  leave.s  loc_74A3B
0x74a3b  ldloc.s  5
0x74a3d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x74a42  brtrue   loc_7498B
0x74a47  leave.s  loc_74A5E
0x74a49  ldloc.s  5
0x74a4b  isinst   [mscorlib]System.IDisposable
0x74a50  stloc.s  6
0x74a52  ldloc.s  6
0x74a54  brfalse.s loc_74A5D
0x74a56  ldloc.s  6
0x74a58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74a5d  endfinally
0x74a5e  ldloc.2
0x74a5f  brfalse.s loc_74A99
0x74a61  ldarg.0
0x74a62  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore <>c__DisplayClass3::<>4__this
0x74a67  ldarg.0
0x74a68  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite <>c__DisplayClass3::site
0x74a6d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_WebApplication()
0x74a72  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x74a77  ldarg.0
0x74a78  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite <>c__DisplayClass3::site
0x74a7d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ContentDatabase()
0x74a82  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x74a87  ldarg.0
0x74a88  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite <>c__DisplayClass3::site
0x74a8d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x74a92  ldloc.0
0x74a93  ldloc.1
0x74a94  call     instance void Microsoft.SharePoint.Taxonomy.TermStore::AddUsedTerms(valuetype [mscorlib]System.Guid webAppId, valuetype [mscorlib]System.Guid contentDatabaseId, valuetype [mscorlib]System.Guid siteId, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> termSetIds, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> termIds)
0x74a99  leave.s  loc_74AB4
0x74a9b  pop
0x74a9c  ldc.i4   0x67316D76
0x74aa1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x74aa6  ldc.i4.s 0xA
0x74aa8  ldstr    aUpdateusedterm_1// "UpdateUsedTermsOnSite stopped due to nu"...
0x74aad  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x74ab2  leave.s  loc_74AB4
0x74ab4  ret
```
