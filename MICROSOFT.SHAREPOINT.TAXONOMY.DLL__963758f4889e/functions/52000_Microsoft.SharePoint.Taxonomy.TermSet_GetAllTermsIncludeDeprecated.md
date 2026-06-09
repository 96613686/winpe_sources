# Microsoft.SharePoint.Taxonomy.TermSet::GetAllTermsIncludeDeprecated

- ea: `0x52000`
- end: `0x520d8`
- name: `Microsoft.SharePoint.Taxonomy.TermSet::GetAllTermsIncludeDeprecated`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5a9f0`
- `0x74d10`

## callees

- `0x2f7e0`
- `0x33220`
- `0x48810`
- `0x48a60`
- `0x48ac0`
- `0x4db80`
- `0x516d0`
- `0x52000`
- `0x536f0`
- `0x56bd0`

## string_xrefs

- `0x5200a`: `WEX_Taxonomy_GetAllTermsIncludeDeprecated`
- `0x52028`: `Begin: TermSet.GetAllTermsIncludeDeprecated()`
- `0x5205a`: `GetAllTermsIncludeDeprecated is called for keyword or hashtag term set {0} from callstack {1}`
- `0x520cc`: `End: TermSet.GetAllTermsIncludeDeprecated()`

## pseudocode

```c

```

## disassembly

```asm
0x52000  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermSet::GetAllTermsIncludeDeprecatedGuid
0x52005  ldstr    a5182016// "5/18/2016"
0x5200a  ldstr    aWexTaxonomyGet// "WEX_Taxonomy_GetAllTermsIncludeDeprecat"...
0x5200f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x52014  brfalse.s loc_5201C
0x52016  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPExperimentalFeatureException::.ctor()
0x5201b  throw
0x5201c  ldc.i4   0x1218606
0x52021  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52026  ldc.i4.s 0x64
0x52028  ldstr    aBeginTermsetGe_0// "Begin: TermSet.GetAllTermsIncludeDeprec"...
0x5202d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x52032  ldarg.0
0x52033  call     instance valuetype Microsoft.SharePoint.Taxonomy.Internal.TermSetType Microsoft.SharePoint.Taxonomy.TermSet::get_Type()
0x52038  ldc.i4.1
0x52039  beq.s    loc_52048
0x5203b  ldarg.0
0x5203c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x52041  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet::get_IsHashTagsTermSet()
0x52046  brfalse.s loc_5208D
0x52048  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x5204d  stloc.0
0x5204e  ldc.i4   0x1218607
0x52053  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x52058  ldc.i4.s 0x32
0x5205a  ldstr    aGetalltermsinc// "GetAllTermsIncludeDeprecated is called "...
0x5205f  ldc.i4.2
0x52060  newarr   [mscorlib]System.Object
0x52065  stloc.3
0x52066  ldloc.3
0x52067  ldc.i4.0
0x52068  ldarg.0
0x52069  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x5206e  stloc.s  4
0x52070  ldloca.s 4
0x52072  constrained. [mscorlib]System.Guid
0x52078  callvirt instance string [mscorlib]System.Object::ToString()
0x5207d  stelem.ref
0x5207e  ldloc.3
0x5207f  ldc.i4.1
0x52080  ldloc.0
0x52081  callvirt instance string [mscorlib]System.Object::ToString()
0x52086  stelem.ref
0x52087  ldloc.3
0x52088  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5208d  ldarg.0
0x5208e  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x52093  ldarg.0
0x52094  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x52099  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x5209e  ldarg.0
0x5209f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x520a4  ldc.i4.1
0x520a5  ldc.i4.1
0x520a6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetTermSetWithAllTerms(class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet sharedTermSet, bool includeDeprecated, bool skipCacheSandbox)
0x520ab  stloc.1
0x520ac  ldloc.1
0x520ad  ldarg.0
0x520ae  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet Microsoft.SharePoint.Taxonomy.TermSetItem::get_SharedTermSet()
0x520b3  ldarg.0
0x520b4  call     instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_TermStore()
0x520b9  ldc.i4.1
0x520ba  call     class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermCollection::CreateTermCollection(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm> sharedTerms, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermSet sharedTermSet, class Microsoft.SharePoint.Taxonomy.TermStore termStore, bool shouldSort)
0x520bf  stloc.2
0x520c0  ldc.i4   0x1218608
0x520c5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x520ca  ldc.i4.s 0x64
0x520cc  ldstr    aEndTermsetGeta_0// "End: TermSet.GetAllTermsIncludeDeprecat"...
0x520d1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x520d6  ldloc.2
0x520d7  ret
```
