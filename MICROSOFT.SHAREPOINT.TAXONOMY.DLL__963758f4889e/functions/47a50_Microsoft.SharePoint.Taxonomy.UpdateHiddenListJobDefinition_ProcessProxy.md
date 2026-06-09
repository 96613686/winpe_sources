# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::ProcessProxy

- ea: `0x47a50`
- end: `0x47fbb`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::ProcessProxy`
- size: `1387`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x46a10`

## callees

- `0x43c80`
- `0x44290`
- `0x46ca0`
- `0x46d50`
- `0x46e40`
- `0x46f90`
- `0x47430`
- `0x479f0`
- `0x47a50`
- `0x484e0`
- `0x486c0`
- `0x53c10`
- `0x65280`
- `0x66690`
- `0x66880`

## string_xrefs

- `0x47a7e`: `Gave up trying to access Managed Metadata service application proxy '{0}'`
- `0x47aad`: `Timed out trying to connect to Managed Metadata service application proxy '{0}'.  Retrying.`
- `0x47aef`: `Checking for term store changes in web app {0} for Term Store {1} in UpdateHiddenList timer job`
- `0x47bd2`: `Trying to update a site but the hidden list is null`
- `0x47c45`: `Hidden list is being updated for a site ID {0}`
- `0x47cf9`: `Error updating site during taxonomy hidden list timer job.  Site - {0}, Proxy {1}, error {2}`
- `0x47d76`: `Error updating site during taxonomy hidden list timer job.  Site - {0}, Proxy {1}, error {2}.  This may be expected if the site has been deleted.`
- `0x47e60`: `Error updating service database last update timestamp.  Error: {0}`
- `0x47ee2`: `Error updating content database last update timestamp.  Proxy: {0} Db: {1} Error: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x47a50  ldarg.0
0x47a51  ldnull
0x47a52  stfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x47a57  ldc.i4.0
0x47a58  stloc.0
0x47a59  ldarg.1
0x47a5a  callvirt instance class Microsoft.SharePoint.Taxonomy.PartitionSettings Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::ReadServiceApplicationSettings()
0x47a5f  stloc.2
0x47a60  ldloc.2
0x47a61  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.PartitionSettings::termStoreId
0x47a66  stloc.1
0x47a67  leave.s  loc_47AD7
0x47a69  pop
0x47a6a  ldloc.0
0x47a6b  ldc.i4.1
0x47a6c  add.ovf
0x47a6d  stloc.0
0x47a6e  ldloc.0
0x47a6f  ldc.i4.5
0x47a70  blt.s    loc_47AA1
0x47a72  ldc.i4   0x7A06C0
0x47a77  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47a7c  ldc.i4.s 0xA
0x47a7e  ldstr    aGaveUpTryingTo// "Gave up trying to access Managed Metada"...
0x47a83  ldc.i4.1
0x47a84  newarr   [mscorlib]System.Object
0x47a89  stloc.s  0x1B
0x47a8b  ldloc.s  0x1B
0x47a8d  ldc.i4.0
0x47a8e  ldarg.1
0x47a8f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47a94  stelem.ref
0x47a95  ldloc.s  0x1B
0x47a97  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47a9c  leave    loc_47B53
0x47aa1  ldc.i4   0x21C29D
0x47aa6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47aab  ldc.i4.s 0xF
0x47aad  ldstr    aTimedOutTrying// "Timed out trying to connect to Managed "...
0x47ab2  ldc.i4.1
0x47ab3  newarr   [mscorlib]System.Object
0x47ab8  stloc.s  0x1C
0x47aba  ldloc.s  0x1C
0x47abc  ldc.i4.0
0x47abd  ldarg.1
0x47abe  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47ac3  stelem.ref
0x47ac4  ldloc.s  0x1C
0x47ac6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47acb  ldc.i4   0x4E20
0x47ad0  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x47ad5  leave.s  loc_47A59
0x47ad7  ldnull
0x47ad8  stloc.3
0x47ad9  ldarg.0
0x47ada  ldarg.1
0x47adb  ldloc.1
0x47adc  ldloca.s 3
0x47ade  call     instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::CheckForSiteRestore(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [mscorlib]System.Guid allPartitionTermStoreId, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, string>& databaseChangeTokens)
0x47ae3  ldc.i4   0x636D6332
0x47ae8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47aed  ldc.i4.s 0x64
0x47aef  ldstr    aCheckingForTer_2// "Checking for term store changes in web "...
0x47af4  ldc.i4.2
0x47af5  newarr   [mscorlib]System.Object
0x47afa  stloc.s  0x1D
0x47afc  ldloc.s  0x1D
0x47afe  ldc.i4.0
0x47aff  ldarg.0
0x47b00  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x47b05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47b0a  box      [mscorlib]System.Guid
0x47b0f  stelem.ref
0x47b10  ldloc.s  0x1D
0x47b12  ldc.i4.1
0x47b13  ldarg.1
0x47b14  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47b19  stelem.ref
0x47b1a  ldloc.s  0x1D
0x47b1c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47b21  ldnull
0x47b22  stloc.s  4
0x47b24  ldarg.0
0x47b25  ldarg.1
0x47b26  ldloc.1
0x47b27  ldloca.s 4
0x47b29  ldloca.s 6
0x47b2b  ldloca.s 5
0x47b2d  call     instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetTermstoreChanges(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [mscorlib]System.Guid allPartitionTermStoreId, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>& partitionToSiteToTermSetToTermMappings, [out] valuetype [mscorlib]System.DateTime& previousUpdate, [out] valuetype [mscorlib]System.DateTime& currentUpdate)
0x47b32  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x47b37  stloc.s  7
0x47b39  ldloc.s  4
0x47b3b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::get_Count()
0x47b40  brtrue.s loc_47B54
0x47b42  ldloc.3
0x47b43  brfalse.s loc_47B4D
0x47b45  ldloc.3
0x47b46  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, string>::get_Count()
0x47b4b  brtrue.s loc_47B54
0x47b4d  ldarg.1
0x47b4e  call     void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::CleanUpECMChangeLog(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy)
0x47b53  ret
0x47b54  ldloc.s  4
0x47b56  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::GetEnumerator()
0x47b5b  stloc.s  0x1E
0x47b5d  br       loc_47DCF
0x47b62  ldloca.s 0x1E
0x47b64  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::get_Current()
0x47b69  stloc.s  8
0x47b6b  ldarg.0
0x47b6c  ldnull
0x47b6d  stfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x47b72  ldloca.s 8
0x47b74  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::get_Value()
0x47b79  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>::GetEnumerator()
0x47b7e  stloc.s  0x1F
0x47b80  br       loc_47DB3
0x47b85  ldloca.s 0x1F
0x47b87  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>::get_Current()
0x47b8c  stloc.s  9
0x47b8e  ldloca.s 9
0x47b90  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>::get_Key()
0x47b95  stloc.s  0xA
0x47b97  ldloc.s  7
0x47b99  ldloc.s  0xA
0x47b9b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x47ba0  brtrue   loc_47DAC
0x47ba5  ldloc.s  0xA
0x47ba7  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(valuetype [mscorlib]System.Guid)
0x47bac  stloc.s  0xB
0x47bae  ldarg.0
0x47baf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x47bb4  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::listItemIdsForCatalogPush
0x47bb9  ldloc.s  0xB
0x47bbb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.TaxonomyField::GetLookupList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x47bc0  stloc.s  0xC
0x47bc2  ldloc.s  0xC
0x47bc4  brtrue.s loc_47BE1
0x47bc6  ldc.i4   0x32636B71
0x47bcb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47bd0  ldc.i4.s 0xA
0x47bd2  ldstr    aTryingToUpdate// "Trying to update a site but the hidden "...
0x47bd7  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x47bdc  leave    loc_47DB3
0x47be1  ldloc.s  0xB
0x47be3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x47be8  brtrue.s loc_47BF7
0x47bea  ldarg.1
0x47beb  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceApplicationPartitioned()
0x47bf0  brfalse.s loc_47BF7
0x47bf2  leave    loc_47DBF
0x47bf7  ldarg.0
0x47bf8  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x47bfd  brtrue.s loc_47C0D
0x47bff  ldarg.0
0x47c00  ldarg.1
0x47c01  ldloc.s  0xB
0x47c03  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStore::.ctor(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy applicationProxy, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x47c08  stfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x47c0d  ldloca.s 9
0x47c0f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>::get_Value()
0x47c14  stloc.s  0xD
0x47c16  ldloc.s  0xD
0x47c18  brfalse  loc_47D4B
0x47c1d  ldloc.s  0xD
0x47c1f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>::get_Keys()
0x47c24  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>::GetEnumerator()
0x47c29  stloc.s  0x20
0x47c2b  br       loc_47D2F
0x47c30  ldloca.s 0x20
0x47c32  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>::get_Current()
0x47c37  stloc.s  0xE
0x47c39  ldc.i4   0x32636B70
0x47c3e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47c43  ldc.i4.s 0x32
0x47c45  ldstr    aHiddenListIsBe// "Hidden list is being updated for a site"...
0x47c4a  ldc.i4.1
0x47c4b  newarr   [mscorlib]System.Object
0x47c50  stloc.s  0x21
0x47c52  ldloc.s  0x21
0x47c54  ldc.i4.0
0x47c55  ldloc.s  0xB
0x47c57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_ID()
0x47c5c  box      [mscorlib]System.Guid
0x47c61  stelem.ref
0x47c62  ldloc.s  0x21
0x47c64  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47c69  ldloc.s  0xC
0x47c6b  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_IsThrottled()
0x47c70  stloc.s  0xF
0x47c72  ldloc.s  0xD
0x47c74  ldloc.s  0xE
0x47c76  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>::get_Item(void)
0x47c7b  ldloc.s  0xF
0x47c7d  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::BuildCamlQueries(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> terms, bool useIndex)
0x47c82  stloc.s  0x10
0x47c84  ldloc.s  0x10
0x47c86  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x47c8b  stloc.s  0x22
0x47c8d  br.s     loc_47CD0
0x47c8f  ldloca.s 0x22
0x47c91  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x47c96  stloc.s  0x11
0x47c98  ldc.i4   0x67326F6E
0x47c9d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47ca2  ldc.i4.s 0x32
0x47ca4  ldstr    aSearchQueryIs0// "Search query is {0}"
0x47ca9  ldc.i4.1
0x47caa  newarr   [mscorlib]System.Object
0x47caf  stloc.s  0x23
0x47cb1  ldloc.s  0x23
0x47cb3  ldc.i4.0
0x47cb4  ldloc.s  0x11
0x47cb6  stelem.ref
0x47cb7  ldloc.s  0x23
0x47cb9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47cbe  ldarg.0
0x47cbf  ldloc.s  0xB
0x47cc1  ldloc.s  0xC
0x47cc3  ldloc.s  0x11
0x47cc5  ldarg.0
0x47cc6  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::termStore
0x47ccb  call     instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::UpdateSiteHiddenList(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, class [Microsoft.SharePoint]Microsoft.SharePoint.SPList hiddenList, string queryForGettingUpdateItems, class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x47cd0  ldloca.s 0x22
0x47cd2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x47cd7  brtrue.s loc_47C8F
0x47cd9  leave.s  loc_47CE9
0x47cdb  ldloca.s 0x22
0x47cdd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x47ce3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47ce8  endfinally
0x47ce9  leave.s  loc_47D2F
0x47ceb  stloc.s  0x12
0x47ced  ldc.i4   0x636D6333
0x47cf2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47cf7  ldc.i4.s 0xA
0x47cf9  ldstr    aErrorUpdatingS// "Error updating site during taxonomy hid"...
0x47cfe  ldc.i4.3
0x47cff  newarr   [mscorlib]System.Object
0x47d04  stloc.s  0x24
0x47d06  ldloc.s  0x24
0x47d08  ldc.i4.0
0x47d09  ldloc.s  0xB
0x47d0b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x47d10  stelem.ref
0x47d11  ldloc.s  0x24
0x47d13  ldc.i4.1
0x47d14  ldarg.1
0x47d15  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47d1a  stelem.ref
0x47d1b  ldloc.s  0x24
0x47d1d  ldc.i4.2
0x47d1e  ldloc.s  0x12
0x47d20  callvirt instance string [mscorlib]System.Object::ToString()
0x47d25  stelem.ref
0x47d26  ldloc.s  0x24
0x47d28  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47d2d  leave.s  loc_47D2F
0x47d2f  ldloca.s 0x20
0x47d31  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>::MoveNext()
0x47d36  brtrue   loc_47C30
0x47d3b  leave.s  loc_47D4B
0x47d3d  ldloca.s 0x20
0x47d3f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>
0x47d45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47d4a  endfinally
0x47d4b  ldloc.s  0xB
0x47d4d  ldarg.0
0x47d4e  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::listItemIdsForCatalogPush
0x47d53  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::UpdateCatalogListItems(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, class [mscorlib]System.Collections.Generic.List`1<int32> listItemIdsForCatalogPush)
0x47d58  leave.s  loc_47D66
0x47d5a  ldloc.s  0xB
0x47d5c  brfalse.s loc_47D65
0x47d5e  ldloc.s  0xB
0x47d60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47d65  endfinally
0x47d66  leave.s  loc_47DAC
0x47d68  stloc.s  0x13
0x47d6a  ldc.i4   0x10E651
0x47d6f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47d74  ldc.i4.s 0x14
0x47d76  ldstr    aErrorUpdatingS_0// "Error updating site during taxonomy hid"...
0x47d7b  ldc.i4.3
0x47d7c  newarr   [mscorlib]System.Object
0x47d81  stloc.s  0x25
0x47d83  ldloc.s  0x25
0x47d85  ldc.i4.0
0x47d86  ldloc.s  0xA
0x47d88  box      [mscorlib]System.Guid
0x47d8d  stelem.ref
0x47d8e  ldloc.s  0x25
0x47d90  ldc.i4.1
0x47d91  ldarg.1
0x47d92  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47d97  stelem.ref
0x47d98  ldloc.s  0x25
0x47d9a  ldc.i4.2
0x47d9b  ldloc.s  0x13
0x47d9d  callvirt instance string [mscorlib]System.Object::ToString()
0x47da2  stelem.ref
  ... truncated ...
```
