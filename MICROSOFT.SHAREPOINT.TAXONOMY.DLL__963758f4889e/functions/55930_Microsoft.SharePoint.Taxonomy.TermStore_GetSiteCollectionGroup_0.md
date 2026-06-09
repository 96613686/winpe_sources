# Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroup_0

- ea: `0x55930`
- end: `0x55bb6`
- name: `Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroup_0`
- size: `646`
- prototype: ``
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x2dc50`
- `0x54ca0`
- `0x558e0`
- `0x55920`
- `0x701f0`

## callees

- `0x2acd0`
- `0x2f180`
- `0x2f1c0`
- `0x2fc20`
- `0x487f0`
- `0x48810`
- `0x48b70`
- `0x497d0`
- `0x49a20`
- `0x49d10`
- `0x540b0`
- `0x55630`
- `0x55930`
- `0x55bc0`
- `0x55f90`
- `0x56bd0`
- `0x57240`

## string_xrefs

- `0x559a7`: `Attempt was made to access a non-site collection group as a site collection group.  Group {0}, site ID {1}`
- `0x559fc`: `Site collection has insufficient access to local site collection group.  Group {0}, site collection {1} with ID {2}`
- `0x55baa`: `Created Site Collection TermSet Group`

## pseudocode

```c

```

## disassembly

```asm
0x55930  ldnull
0x55931  stloc.0
0x55932  ldc.i4.0
0x55933  stloc.1
0x55934  ldarg.1
0x55935  brfalse  loc_55BB4
0x5593a  ldarg.0
0x5593b  ldarg.1
0x5593c  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroupId(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x55941  stloc.2
0x55942  ldloc.2
0x55943  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x55948  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5594d  brfalse  loc_55A33
0x55952  ldarg.0
0x55953  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager Microsoft.SharePoint.Taxonomy.TermStore::get_ObjectManager()
0x55958  ldloc.2
0x55959  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Internal.SharedItemManager::GetGroup(valuetype [mscorlib]System.Guid groupGuid)
0x5595e  stloc.3
0x5595f  ldloc.3
0x55960  brfalse  loc_559ED
0x55965  ldloc.3
0x55966  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x5596b  ldarg.1
0x5596c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x55971  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x55976  brtrue.s loc_55985
0x55978  ldloc.3
0x55979  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x5597e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x55983  brtrue.s loc_559ED
0x55985  ldloc.3
0x55986  ldarg.0
0x55987  call     class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.Group::CreateGroup(class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup sharedGroup, class Microsoft.SharePoint.Taxonomy.TermStore termStore)
0x5598c  stloc.0
0x5598d  ldloc.0
0x5598e  brfalse  loc_55A33
0x55993  ldloc.0
0x55994  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSiteCollectionGroup()
0x55999  brtrue.s loc_559E4
0x5599b  ldc.i4   0x67716539
0x559a0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x559a5  ldc.i4.s 0x14
0x559a7  ldstr    aAttemptWasMade// "Attempt was made to access a non-site c"...
0x559ac  ldc.i4.2
0x559ad  newarr   [mscorlib]System.Object
0x559b2  stloc.s  9
0x559b4  ldloc.s  9
0x559b6  ldc.i4.0
0x559b7  ldloc.3
0x559b8  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_Name()
0x559bd  stelem.ref
0x559be  ldloc.s  9
0x559c0  ldc.i4.1
0x559c1  ldarg.1
0x559c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x559c7  box      [mscorlib]System.Guid
0x559cc  stelem.ref
0x559cd  ldloc.s  9
0x559cf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x559d4  ldstr    aTmtgenericexce// "TMTGenericException"
0x559d9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x559de  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x559e3  throw
0x559e4  ldloc.0
0x559e5  ldarg.1
0x559e6  callvirt instance void Microsoft.SharePoint.Taxonomy.Group::TryAddSiteCollectionIdsIfEmpty(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x559eb  br.s     loc_55A33
0x559ed  ldloc.3
0x559ee  brfalse.s loc_55A33
0x559f0  ldc.i4   0x67716630
0x559f5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x559fa  ldc.i4.s 0x14
0x559fc  ldstr    aSiteCollection_0// "Site collection has insufficient access"...
0x55a01  ldc.i4.3
0x55a02  newarr   [mscorlib]System.Object
0x55a07  stloc.s  0xA
0x55a09  ldloc.s  0xA
0x55a0b  ldc.i4.0
0x55a0c  ldloc.3
0x55a0d  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_Name()
0x55a12  stelem.ref
0x55a13  ldloc.s  0xA
0x55a15  ldc.i4.1
0x55a16  ldarg.1
0x55a17  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ServerRelativeUrl()
0x55a1c  stelem.ref
0x55a1d  ldloc.s  0xA
0x55a1f  ldc.i4.2
0x55a20  ldarg.1
0x55a21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x55a26  box      [mscorlib]System.Guid
0x55a2b  stelem.ref
0x55a2c  ldloc.s  0xA
0x55a2e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x55a33  ldloc.0
0x55a34  brtrue   loc_55AFC
0x55a39  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x55a3e  brfalse  loc_55AFC
0x55a43  ldarg.1
0x55a44  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x55a49  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x55a4e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x55a53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x55a58  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x55a5d  brfalse  loc_55AFC
0x55a62  ldarg.0
0x55a63  ldc.i4.1
0x55a64  stfld    bool Microsoft.SharePoint.Taxonomy.TermStore::isGettingSiteCollectionGroup
0x55a69  ldarg.0
0x55a6a  call     instance class Microsoft.SharePoint.Taxonomy.GroupCollection Microsoft.SharePoint.Taxonomy.TermStore::get_Groups()
0x55a6f  stloc.s  4
0x55a71  ldarg.0
0x55a72  ldc.i4.0
0x55a73  stfld    bool Microsoft.SharePoint.Taxonomy.TermStore::isGettingSiteCollectionGroup
0x55a78  ldarg.1
0x55a79  call     string Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroupName(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x55a7e  stloc.s  5
0x55a80  ldloc.s  4
0x55a82  brfalse.s loc_55AFC
0x55a84  ldloc.s  4
0x55a86  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Group>::GetEnumerator()
0x55a8b  stloc.s  0xB
0x55a8d  br.s     loc_55AE5
0x55a8f  ldloc.s  0xB
0x55a91  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Group>::get_Current()
0x55a96  stloc.s  6
0x55a98  ldloc.s  6
0x55a9a  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSiteCollectionGroup()
0x55a9f  brfalse.s loc_55AE5
0x55aa1  ldloc.s  6
0x55aa3  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Name()
0x55aa8  ldloc.s  5
0x55aaa  ldc.i4.5
0x55aab  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x55ab0  brfalse.s loc_55AE5
0x55ab2  ldloc.s  6
0x55ab4  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x55ab9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x55abe  ldarg.1
0x55abf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x55ac4  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x55ac9  brtrue.s loc_55ADE
0x55acb  ldloc.s  6
0x55acd  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedGroup Microsoft.SharePoint.Taxonomy.Group::get_SharedGroup()
0x55ad2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Internal.SharedGroup::get_SiteCollectionIds()
0x55ad7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x55adc  brtrue.s loc_55AE5
0x55ade  ldc.i4.1
0x55adf  stloc.1
0x55ae0  ldloc.s  6
0x55ae2  stloc.0
0x55ae3  br.s     loc_55AEE
0x55ae5  ldloc.s  0xB
0x55ae7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x55aec  brtrue.s loc_55A8F
0x55aee  leave.s  loc_55AFC
0x55af0  ldloc.s  0xB
0x55af2  brfalse.s loc_55AFB
0x55af4  ldloc.s  0xB
0x55af6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55afb  endfinally
0x55afc  leave.s  loc_55B04
0x55afe  pop
0x55aff  leave.s  loc_55B04
0x55b01  pop
0x55b02  leave.s  loc_55B04
0x55b04  ldloc.1
0x55b05  brtrue.s loc_55B13
0x55b07  ldloc.0
0x55b08  brtrue   loc_55BB4
0x55b0d  ldarg.2
0x55b0e  brfalse  loc_55BB4
0x55b13  ldloc.1
0x55b14  brtrue.s loc_55B24
0x55b16  ldarg.0
0x55b17  ldarg.1
0x55b18  call     string Microsoft.SharePoint.Taxonomy.TermStore::GetSiteCollectionGroupName(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x55b1d  ldarg.1
0x55b1e  call     instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermStore::CreateSiteCollectionGroup(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite currentSite)
0x55b23  stloc.0
0x55b24  ldc.i4   0x40000
0x55b29  conv.i8
0x55b2a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurity/GrantAdditionalPermissionsInScope::.ctor(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions)
0x55b2f  stloc.s  7
0x55b31  ldarg.1
0x55b32  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x55b37  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_AllowUnsafeUpdates()
0x55b3c  stloc.s  8
0x55b3e  ldarg.1
0x55b3f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x55b44  ldc.i4.1
0x55b45  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AllowUnsafeUpdates(bool)
0x55b4a  ldarg.1
0x55b4b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x55b50  callvirt instance class [mscorlib]System.Collections.Hashtable [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_AllProperties()
0x55b55  ldarg.0
0x55b56  call     instance string Microsoft.SharePoint.Taxonomy.TermStore::get_SiteCollectionGroupKey()
0x55b5b  ldloc.0
0x55b5c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x55b61  stloc.s  0xC
0x55b63  ldloca.s 0xC
0x55b65  constrained. [mscorlib]System.Guid
0x55b6b  callvirt instance string [mscorlib]System.Object::ToString()
0x55b70  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x55b75  ldarg.1
0x55b76  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x55b7b  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::Update()
0x55b80  leave.s  loc_55B90
0x55b82  ldarg.1
0x55b83  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x55b88  ldloc.s  8
0x55b8a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::set_AllowUnsafeUpdates(bool)
0x55b8f  endfinally
0x55b90  leave.s  loc_55B9E
0x55b92  ldloc.s  7
0x55b94  brfalse.s loc_55B9D
0x55b96  ldloc.s  7
0x55b98  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55b9d  endfinally
0x55b9e  ldc.i4   0x37787467
0x55ba3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x55ba8  ldc.i4.s 0x32
0x55baa  ldstr    aCreatedSiteCol// "Created Site Collection TermSet Group"
0x55baf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x55bb4  ldloc.0
0x55bb5  ret
```
