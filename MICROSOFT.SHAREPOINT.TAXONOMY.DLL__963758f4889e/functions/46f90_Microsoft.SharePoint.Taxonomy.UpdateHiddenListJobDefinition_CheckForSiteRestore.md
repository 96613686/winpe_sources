# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::CheckForSiteRestore

- ea: `0x46f90`
- end: `0x4742d`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::CheckForSiteRestore`
- size: `1181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x47a50`

## callees

- `0x46db0`
- `0x46f90`
- `0x53c10`
- `0x55c80`
- `0x65280`

## string_xrefs

- `0x46fa9`: `Checking for restored site collection in web app {0} for term store {1} in UpdateHiddenList timer job`
- `0x47054`: `Failed to get changes in content db {0} web app {1} for term store {2} in UpdateHiddenList timer job.`
- `0x470d1`: `Failed to get changes in content db {0} web app {1} for term store {2} in UpdateHiddenList timer job after clearing out change token.  No changes exist - skipping Content DB.`
- `0x47172`: `Found change log for restored site collection {0} in web app {1} for term store {2} in UpdateHiddenList timer job`
- `0x47264`: `Full hidden list sync starting on site {0} in web app {1} for term store {2} in UpdateHiddenList timer job`
- `0x472be`: `Not syncing on site {0} in web app {1} for term store {2} in UpdateHiddenList timer job.  Proxy is partitioned, site is not.`
- `0x4731c`: `Full hidden list sync completed on site {0} in web app {1} for term store {2} in UpdateHiddenList timer job`

## pseudocode

```c

```

## disassembly

```asm
0x46f90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x46f95  stloc.0
0x46f96  ldarg.3
0x46f97  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, string>::.ctor()
0x46f9c  stind.ref
0x46f9d  ldc.i4   0x636D6232
0x46fa2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x46fa7  ldc.i4.s 0x64
0x46fa9  ldstr    aCheckingForRes// "Checking for restored site collection i"...
0x46fae  ldc.i4.2
0x46faf  newarr   [mscorlib]System.Object
0x46fb4  stloc.s  0xE
0x46fb6  ldloc.s  0xE
0x46fb8  ldc.i4.0
0x46fb9  ldarg.0
0x46fba  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46fbf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x46fc4  box      [mscorlib]System.Guid
0x46fc9  stelem.ref
0x46fca  ldloc.s  0xE
0x46fcc  ldc.i4.1
0x46fcd  ldarg.1
0x46fce  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x46fd3  stelem.ref
0x46fd4  ldloc.s  0xE
0x46fd6  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x46fdb  ldarg.0
0x46fdc  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46fe1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabaseCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_ContentDatabases()
0x46fe6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabaseCollection::GetEnumerator()
0x46feb  stloc.s  0xF
0x46fed  br       loc_4721F
0x46ff2  ldloc.s  0xF
0x46ff4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::get_Current()
0x46ff9  stloc.1
0x46ffa  ldarg.0
0x46ffb  ldloc.1
0x46ffc  ldarg.2
0x46ffd  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetChangeToken(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDB, valuetype [mscorlib]System.Guid allPartitionTermStoreId)
0x47002  stloc.2
0x47003  ldc.i4.0
0x47004  ldc.i4.0
0x47005  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::.ctor(bool, bool)
0x4700a  stloc.3
0x4700b  ldloc.3
0x4700c  ldc.i4.1
0x4700d  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Restore(bool)
0x47012  ldloc.3
0x47013  ldc.i4.1
0x47014  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_Site(bool)
0x47019  ldloc.3
0x4701a  ldloc.1
0x4701b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::get_CurrentChangeToken()
0x47020  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenEnd(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x47025  ldloc.2
0x47026  ldnull
0x47027  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x4702c  brfalse.s loc_47035
0x4702e  ldloc.3
0x4702f  ldloc.2
0x47030  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenStart(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x47035  ldnull
0x47036  stloc.s  4
0x47038  ldloc.1
0x47039  ldloc.3
0x4703a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::GetChanges(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery)
0x4703f  stloc.s  4
0x47041  leave    loc_4711D
0x47046  stloc.s  5
0x47048  ldc.i4   0x198840
0x4704d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47052  ldc.i4.s 0x32
0x47054  ldstr    aFailedToGetCha// "Failed to get changes in content db {0}"...
0x47059  ldc.i4.3
0x4705a  newarr   [mscorlib]System.Object
0x4705f  stloc.s  0x10
0x47061  ldloc.s  0x10
0x47063  ldc.i4.0
0x47064  ldloc.1
0x47065  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4706a  box      [mscorlib]System.Guid
0x4706f  stelem.ref
0x47070  ldloc.s  0x10
0x47072  ldc.i4.1
0x47073  ldarg.0
0x47074  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x47079  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4707e  box      [mscorlib]System.Guid
0x47083  stelem.ref
0x47084  ldloc.s  0x10
0x47086  ldc.i4.2
0x47087  ldarg.1
0x47088  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x4708d  stelem.ref
0x4708e  ldloc.s  0x10
0x47090  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47095  ldloc.s  5
0x47097  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x4709c  ldc.i4   0xBC
0x470a1  bne.un.s loc_47119
0x470a3  ldloc.3
0x470a4  ldnull
0x470a5  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::set_ChangeTokenStart(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0x470aa  ldloc.1
0x470ab  ldloc.3
0x470ac  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::GetChanges(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery)
0x470b1  stloc.s  4
0x470b3  leave.s  loc_4711B
0x470b5  stloc.s  6
0x470b7  ldloc.s  6
0x470b9  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPException::get_ErrorCode()
0x470be  ldc.i4   0xBC
0x470c3  bne.un.s loc_47117
0x470c5  ldc.i4   0x198841
0x470ca  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x470cf  ldc.i4.s 0x32
0x470d1  ldstr    aFailedToGetCha_0// "Failed to get changes in content db {0}"...
0x470d6  ldc.i4.3
0x470d7  newarr   [mscorlib]System.Object
0x470dc  stloc.s  0x11
0x470de  ldloc.s  0x11
0x470e0  ldc.i4.0
0x470e1  ldloc.1
0x470e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x470e7  box      [mscorlib]System.Guid
0x470ec  stelem.ref
0x470ed  ldloc.s  0x11
0x470ef  ldc.i4.1
0x470f0  ldarg.0
0x470f1  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x470f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x470fb  box      [mscorlib]System.Guid
0x47100  stelem.ref
0x47101  ldloc.s  0x11
0x47103  ldc.i4.2
0x47104  ldarg.1
0x47105  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x4710a  stelem.ref
0x4710b  ldloc.s  0x11
0x4710d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x47112  leave    loc_4721F
0x47117  rethrow
0x47119  rethrow
0x4711b  leave.s  loc_4711D
0x4711d  ldloc.s  4
0x4711f  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x47124  stloc.s  0x12
0x47126  br       loc_471B4
0x4712b  ldloc.s  0x12
0x4712d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x47132  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPChange
0x47137  stloc.s  7
0x47139  ldloc.s  7
0x4713b  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeSite
0x47140  stloc.s  8
0x47142  ldloc.s  8
0x47144  brfalse.s loc_471B4
0x47146  ldloc.s  8
0x47148  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPChange::get_SiteId()
0x4714d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x47152  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x47157  brfalse.s loc_471B4
0x47159  ldloc.0
0x4715a  ldloc.s  8
0x4715c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPChange::get_SiteId()
0x47161  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x47166  ldc.i4   0x636D6233
0x4716b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47170  ldc.i4.s 0x32
0x47172  ldstr    aFoundChangeLog// "Found change log for restored site coll"...
0x47177  ldc.i4.3
0x47178  newarr   [mscorlib]System.Object
0x4717d  stloc.s  0x13
0x4717f  ldloc.s  0x13
0x47181  ldc.i4.0
0x47182  ldloc.s  8
0x47184  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPChange::get_SiteId()
0x47189  box      [mscorlib]System.Guid
0x4718e  stelem.ref
0x4718f  ldloc.s  0x13
0x47191  ldc.i4.1
0x47192  ldarg.0
0x47193  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x47198  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4719d  box      [mscorlib]System.Guid
0x471a2  stelem.ref
0x471a3  ldloc.s  0x13
0x471a5  ldc.i4.2
0x471a6  ldarg.1
0x471a7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x471ac  stelem.ref
0x471ad  ldloc.s  0x13
0x471af  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x471b4  ldloc.s  0x12
0x471b6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x471bb  brtrue   loc_4712B
0x471c0  leave.s  loc_471D7
0x471c2  ldloc.s  0x12
0x471c4  isinst   [mscorlib]System.IDisposable
0x471c9  stloc.s  0x14
0x471cb  ldloc.s  0x14
0x471cd  brfalse.s loc_471D6
0x471cf  ldloc.s  0x14
0x471d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x471d6  endfinally
0x471d7  ldarg.3
0x471d8  ldind.ref
0x471d9  ldloc.1
0x471da  ldloc.3
0x471db  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeQuery::get_ChangeTokenEnd()
0x471e0  callvirt instance string [mscorlib]System.Object::ToString()
0x471e5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, string>::set_Item(var<u1>, !!T0)
0x471ea  leave.s  loc_4721F
0x471ec  stloc.s  9
0x471ee  ldc.i4   0x198842
0x471f3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x471f8  ldloc.s  9
0x471fa  ldstr    aFailedToGetRes// "Failed to get restore event for content"...
0x471ff  ldc.i4.1
0x47200  newarr   [mscorlib]System.Object
0x47205  stloc.s  0x15
0x47207  ldloc.s  0x15
0x47209  ldc.i4.0
0x4720a  ldloc.1
0x4720b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47210  box      [mscorlib]System.Guid
0x47215  stelem.ref
0x47216  ldloc.s  0x15
0x47218  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x4721d  leave.s  loc_4721F
0x4721f  ldloc.s  0xF
0x47221  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x47226  brtrue   loc_46FF2
0x4722b  leave.s  loc_47239
0x4722d  ldloc.s  0xF
0x4722f  brfalse.s loc_47238
0x47231  ldloc.s  0xF
0x47233  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47238  endfinally
0x47239  ldloc.0
0x4723a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x4723f  stloc.s  0x16
0x47241  br       loc_47410
0x47246  ldloca.s 0x16
0x47248  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x4724d  stloc.s  0xA
0x4724f  ldloc.s  0xA
0x47251  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(valuetype [mscorlib]System.Guid)
0x47256  stloc.s  0xB
0x47258  ldc.i4   0x636D6234
0x4725d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47262  ldc.i4.s 0x32
0x47264  ldstr    aFullHiddenList// "Full hidden list sync starting on site "...
0x47269  ldc.i4.3
0x4726a  newarr   [mscorlib]System.Object
0x4726f  stloc.s  0x17
0x47271  ldloc.s  0x17
0x47273  ldc.i4.0
0x47274  ldloc.s  0xB
0x47276  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x4727b  stelem.ref
0x4727c  ldloc.s  0x17
0x4727e  ldc.i4.1
0x4727f  ldarg.0
0x47280  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x47285  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4728a  box      [mscorlib]System.Guid
0x4728f  stelem.ref
0x47290  ldloc.s  0x17
0x47292  ldc.i4.2
0x47293  ldarg.1
0x47294  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x47299  stelem.ref
0x4729a  ldloc.s  0x17
0x4729c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x472a1  ldloc.s  0xB
0x472a3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x472a8  brtrue.s loc_472FD
0x472aa  ldarg.1
0x472ab  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceApplicationPartitioned()
0x472b0  brfalse.s loc_472FD
0x472b2  ldc.i4   0x636D6235
0x472b7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x472bc  ldc.i4.s 0x32
0x472be  ldstr    aNotSyncingOnSi// "Not syncing on site {0} in web app {1} "...
0x472c3  ldc.i4.3
0x472c4  newarr   [mscorlib]System.Object
0x472c9  stloc.s  0x18
0x472cb  ldloc.s  0x18
0x472cd  ldc.i4.0
0x472ce  ldloc.s  0xB
0x472d0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x472d5  stelem.ref
0x472d6  ldloc.s  0x18
0x472d8  ldc.i4.1
0x472d9  ldarg.0
0x472da  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x472df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x472e4  box      [mscorlib]System.Guid
0x472e9  stelem.ref
  ... truncated ...
```
