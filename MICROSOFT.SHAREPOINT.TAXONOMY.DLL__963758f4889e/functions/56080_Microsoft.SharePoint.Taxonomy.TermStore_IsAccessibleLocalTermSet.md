# Microsoft.SharePoint.Taxonomy.TermStore::IsAccessibleLocalTermSet

- ea: `0x56080`
- end: `0x56202`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::IsAccessibleLocalTermSet`
- size: `386`
- prototype: ``
- caller_count: `8`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x2f9f0`
- `0x2fa90`
- `0x54710`
- `0x55050`
- `0x56270`
- `0x56750`
- `0x56e80`
- `0x57020`

## callees

- `0x2df10`
- `0x2e8c0`
- `0x2f1c0`
- `0x2f1e0`
- `0x2fc80`
- `0x33220`
- `0x33260`
- `0x333a0`
- `0x387f0`
- `0x48810`
- `0x48b70`
- `0x497d0`
- `0x49a20`
- `0x4cf50`
- `0x55bc0`
- `0x55f50`
- `0x56080`
- `0x56bd0`
- `0x56e70`

## string_xrefs

- `0x5608f`: `IsAccessibleLocalTermSet: sharedTermSet is null`
- `0x561ee`: `IsAccessibleLocalTermSet: Unexpected exception occurred`

## pseudocode

```c

```

## disassembly

```asm
0x56080  ldarg.1
0x56081  brtrue.s loc_5609B
0x56083  ldc.i4   0x1859516
0x56088  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5608d  ldc.i4.s 0x14
0x5608f  ldstr    aIsaccessiblelo_0// "IsAccessibleLocalTermSet: sharedTermSet"...
0x56094  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x56099  ldc.i4.0
0x5609a  ret
0x5609b  ldc.i4.0
0x5609c  stloc.0
0x5609d  ldarg.1
0x5609e  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_GroupId()
0x560a3  stloc.1
0x560a4  ldarg.0
0x560a5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool> Microsoft.SharePoint.Taxonomy.TermStore::knownGroupIds
0x560aa  ldloc.1
0x560ab  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::ContainsKey(var<u1>)
0x560b0  brfalse.s loc_560C4
0x560b2  ldarg.0
0x560b3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool> Microsoft.SharePoint.Taxonomy.TermStore::knownGroupIds
0x560b8  ldloc.1
0x560b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::get_Item(void)
0x560be  stloc.0
0x560bf  br       loc_561DE
0x560c4  ldarg.0
0x560c5  call     instance bool Microsoft.SharePoint.Taxonomy.TermStore::get_IsValidTermStoreManagerRequest()
0x560ca  brfalse.s loc_560E0
0x560cc  ldc.i4.1
0x560cd  stloc.0
0x560ce  ldarg.0
0x560cf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool> Microsoft.SharePoint.Taxonomy.TermStore::knownGroupIds
0x560d4  ldloc.1
0x560d5  ldloc.0
0x560d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::Add(var<u1>, !!T0)
0x560db  br       loc_561DE
0x560e0  ldarg.1
0x560e1  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_Type()
0x560e6  ldc.i4.1
0x560e7  beq.s    loc_560F1
0x560e9  ldarg.1
0x560ea  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_IsHashTagsTermSet()
0x560ef  brfalse.s loc_56105
0x560f1  ldc.i4.1
0x560f2  stloc.0
0x560f3  ldarg.0
0x560f4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool> Microsoft.SharePoint.Taxonomy.TermStore::knownGroupIds
0x560f9  ldloc.1
0x560fa  ldloc.0
0x560fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::Add(var<u1>, !!T0)
0x56100  br       loc_561DE
0x56105  ldarg.0
0x56106  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x5610b  ldloc.1
0x5610c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetGroup(int32 groupId)
0x56111  stloc.2
0x56112  ldloc.2
0x56113  ldarg.0
0x56114  call     class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.Group::CreateGroup(class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup sharedGroup, class Microsoft.SharePoint.Taxonomy.TermStore termStore)
0x56119  stloc.3
0x5611a  ldloc.3
0x5611b  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSiteCollectionGroup()
0x56120  brfalse  loc_561CF
0x56125  ldarg.0
0x56126  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x5612b  brfalse  loc_561D1
0x56130  ldarg.0
0x56131  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x56136  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0x5613b  brfalse  loc_561D1
0x56140  ldarg.0
0x56141  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x56146  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0x5614b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext::get_SiteOrNull()
0x56150  stloc.s  4
0x56152  ldloc.s  4
0x56154  brfalse.s loc_561B6
0x56156  ldloc.2
0x56157  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x5615c  ldloc.s  4
0x5615e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x56163  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x56168  brfalse.s loc_5616E
0x5616a  ldc.i4.1
0x5616b  stloc.0
0x5616c  br.s     loc_561B6
0x5616e  ldloc.2
0x5616f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x56174  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x56179  brtrue.s loc_561A0
0x5617b  ldarg.0
0x5617c  ldloc.s  4
0x5617e  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroupId(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x56183  ldloc.3
0x56184  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x56189  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5618e  brfalse.s loc_5619C
0x56190  ldloc.3
0x56191  ldloc.s  4
0x56193  callvirt instance void Microsoft.SharePoint.Taxonomy.Group::TryAddSiteCollectionIdsIfEmpty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x56198  ldc.i4.1
0x56199  stloc.0
0x5619a  br.s     loc_561B6
0x5619c  ldc.i4.0
0x5619d  stloc.0
0x5619e  br.s     loc_561B6
0x561a0  ldloc.2
0x561a1  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedUrlStringCollection Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionUrls()
0x561a6  ldloc.s  4
0x561a8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x561ad  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedUrlStringCollection::Contains(string urlString)
0x561b2  brfalse.s loc_561B6
0x561b4  ldc.i4.1
0x561b5  stloc.0
0x561b6  ldloc.0
0x561b7  brtrue.s loc_561D1
0x561b9  ldarg.0
0x561ba  call     instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0x561bf  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0x561c4  call     bool Microsoft.SharePoint.Taxonomy.Internal.Security::DoesUserHaveServiceAdminPermissions(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext context)
0x561c9  brfalse.s loc_561D1
0x561cb  ldc.i4.1
0x561cc  stloc.0
0x561cd  br.s     loc_561D1
0x561cf  ldc.i4.1
0x561d0  stloc.0
0x561d1  ldarg.0
0x561d2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool> Microsoft.SharePoint.Taxonomy.TermStore::knownGroupIds
0x561d7  ldloc.1
0x561d8  ldloc.0
0x561d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, bool>::Add(var<u1>, !!T0)
0x561de  leave.s  loc_56200
0x561e0  stloc.s  5
0x561e2  ldc.i4   0x1859517
0x561e7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x561ec  ldloc.s  5
0x561ee  ldstr    aIsaccessiblelo_1// "IsAccessibleLocalTermSet: Unexpected ex"...
0x561f3  ldc.i4.0
0x561f4  newarr   [mscorlib]System.Object
0x561f9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x561fe  leave.s  loc_56200
0x56200  ldloc.0
0x56201  ret
```
