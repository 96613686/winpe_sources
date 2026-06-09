# Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CopyOrMoveSite

- ea: `0xa923d0`
- end: `0xa92f75`
- name: `Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CopyOrMoveSite`
- size: `2981`
- prototype: ``
- caller_count: `2`
- callee_count: `84`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0xa92060`
- `0xa92250`

## callees

- `0x13eb80`
- `0x198970`
- `0x1b7de0`
- `0x1b7df0`
- `0x1c8480`
- `0x1c87b0`
- `0x1c8850`
- `0x1f4430`
- `0x1f7910`
- `0x1f79e0`
- `0x1f7a00`
- `0x232440`
- `0x242050`
- `0x242270`
- `0x242ab0`
- `0x24c770`
- `0x252fc0`
- `0x25c080`
- `0x25c190`
- `0x25c460`
- `0x25c660`
- `0x25c6a0`
- `0x25cd40`
- `0x262270`
- `0x262f30`
- `0x263e60`
- `0x28edb0`
- `0x28eea0`
- `0x28ef00`
- `0x29d070`
- `0x2a1220`
- `0x2e6870`
- `0x52dd50`
- `0x577060`
- `0x577070`
- `0x58fbf0`
- `0x590b30`
- `0x59b330`
- `0x59d130`
- `0x59d150`
- `0x789910`
- `0x88b240`
- `0x8e56f0`
- `0x8e5820`
- `0x8e7040`
- `0x8e7090`
- `0x8e71f0`
- `0x93dae0`
- `0x957470`
- `0xa4f180`

## string_xrefs

- `0xa92490`: `Calling ValidateSiteCollection() for site copy`
- `0xa926c7`: `Copying`
- `0xa92991`: `\n            USE [master]\n            SET IDENTITY_INSERT [{targetDB}]..[EventCache] ON\n            INSERT INTO [{targetDB}]..[EventCache] (\n                EventTime,\n                Id,\n                SiteId,\n                WebId,\n                ListId,\n                ItemId,\n                DocId,\n                Guid0,\n                Int0,\n                Int1,\n                ContentTypeId,\n                ItemName,\n                ItemFullUrl,\n       `
- `0xa929b6`: `\n            USE [master]\n            SET IDENTITY_INSERT [{targetDB}]..[EventCache] ON\n            INSERT INTO [{targetDB}]..[EventCache] (\n                EventTime,\n                Id,\n                SiteId,\n                WebId,\n                ListId,\n                ItemId,\n                DocId,\n                Guid0,\n                Int0,\n                Int1,\n                ContentTypeId,\n                ItemName,\n                ItemFullUrl,\n       `
- `0xa929bf`: `\n            USE [master]\n            SET IDENTITY_INSERT [{targetDB}]..[EventCache] ON\n            INSERT INTO [{targetDB}]..[EventCache] (\n                EventTime,\n                Id,SiteId,\n                WebId,\n                ListId,\n                ItemId,\n                DocId,\n                Guid0,\n                Int0,\n                Int1,\n                ContentTypeId,\n                ItemName,\n                ItemFullUrl,\n                EventType,`
- `0xa92a87`: `SPSiteCollectionCopier.CopyOrMoveSite: {0} EventCache rows were copied.`
- `0xa92b1e`: `DBMoveSiteNotInDatabase`
- `0xa92c0b`: `DBMoveSiteExistsInDatabase`
- `0xa92cfa`: `Failed to Rollback the site collection {0} from the destination content Database. The source site collection remains in its initial state.`
- `0xa92d50`: `Failed to delete site {0}.`
- `0xa92def`: `Cannot rename old site `
- `0xa92df6`: ` on copy.`
- `0xa92ee5`: `It took site {0} {1} to be moved.`
- `0xa92f2a`: `A failed attempt to move site {0} took {1}.`

## pseudocode

```c

```

## disassembly

```asm
0xa923d0  ldnull
0xa923d1  stloc.s  0x23
0xa923d3  ldnull
0xa923d4  stloc.s  0x24
0xa923d6  ldnull
0xa923d7  stloc.s  0x25
0xa923d9  ldnull
0xa923da  stloc.s  0x26
0xa923dc  ldnull
0xa923dd  stloc.s  0x27
0xa923df  ldnull
0xa923e0  stloc.s  0x28
0xa923e2  ldnull
0xa923e3  stloc.s  0x29
0xa923e5  newobj   instance void <>c__DisplayClass12::.ctor()
0xa923ea  stloc.s  0x2A
0xa923ec  ldloc.s  0x2A
0xa923ee  ldarg.s  6
0xa923f0  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass12::newSiteId
0xa923f5  ldloc.s  0x2A
0xa923f7  ldarg.s  7
0xa923f9  stfld    class Microsoft.SharePoint.SPSiteCopyParameters <>c__DisplayClass12::param
0xa923fe  ldarg.2
0xa923ff  brfalse.s loc_A9240F
0xa92401  ldarg.1
0xa92402  callvirt instance bool SPMigratableSite::get_Deleted()
0xa92407  brfalse.s loc_A9240F
0xa92409  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xa9240e  throw
0xa9240f  ldarg.0
0xa92410  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92415  callvirt instance bool Microsoft.SharePoint.Administration.SPDatabase::get_IsReadOnly()
0xa9241a  stloc.0
0xa9241b  ldarg.0
0xa9241c  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92421  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0xa92426  callvirt instance bool Microsoft.SharePoint.Administration.SPFarm::CurrentUserIsAdministrator()
0xa9242b  stloc.1
0xa9242c  ldarg.2
0xa9242d  brfalse.s loc_A92440
0xa9242f  ldarg.s  4
0xa92431  brtrue.s loc_A92440
0xa92433  ldarg.0
0xa92434  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_ToContentDatabase()
0xa92439  call     bool Microsoft.SharePoint.Administration.SPDeletedSite::ExtendedDeletionQueueSupport(class Microsoft.SharePoint.Administration.SPContentDatabase db)
0xa9243e  br.s     loc_A92441
0xa92440  ldc.i4.0
0xa92441  stloc.2
0xa92442  ldarg.0
0xa92443  ldarg.2
0xa92444  ldloc.s  0x2A
0xa92446  ldfld    class Microsoft.SharePoint.SPSiteCopyParameters <>c__DisplayClass12::param
0xa9244b  brtrue.s loc_A92450
0xa9244d  ldc.i4.0
0xa9244e  br.s     loc_A9245C
0xa92450  ldloc.s  0x2A
0xa92452  ldfld    class Microsoft.SharePoint.SPSiteCopyParameters <>c__DisplayClass12::param
0xa92457  callvirt instance bool Microsoft.SharePoint.SPSiteCopyParameters::get_BatchTableCopy()
0xa9245c  call     instance void Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::ValidateDatabases(bool copy, bool batchTableCopy)
0xa92461  ldarg.0
0xa92462  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_RbsProviderMap()
0xa92467  brfalse.s loc_A92480
0xa92469  ldarg.0
0xa9246a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_RbsProviderMap()
0xa9246f  ldarg.0
0xa92470  ldflda   unsigned int8[] Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::m_SourceRbsProviderIds
0xa92475  ldarg.0
0xa92476  ldflda   unsigned int8[] Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::m_TargetRbsProviderIds
0xa9247b  call     void Microsoft.SharePoint.Administration.SPRemoteBlobStorageSettings::GetProviderIdsFromMap(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> rbsProviderMap, [out] unsigned int8[]& sourceRbsProviderIds, [out] unsigned int8[]& targetRbsProviderIds)
0xa92480  ldloc.1
0xa92481  brfalse.s loc_A9248A
0xa92483  ldarg.1
0xa92484  ldc.i4.1
0xa92485  callvirt instance void SPMigratableSite::set_AdministratorOperationMode(bool value)
0xa9248a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xa9248f  stloc.3
0xa92490  ldstr    aCallingValidat// "Calling ValidateSiteCollection() for si"...
0xa92495  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0xa9249a  stloc.s  0x2B
0xa9249c  ldarg.0
0xa9249d  ldarg.1
0xa9249e  ldarg.2
0xa9249f  call     instance void Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::ValidateSiteCollection(class SPMigratableSite msite, bool copy)
0xa924a4  leave.s  loc_A924B2
0xa924a6  ldloc.s  0x2B
0xa924a8  brfalse.s loc_A924B1
0xa924aa  ldloc.s  0x2B
0xa924ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa924b1  endfinally
0xa924b2  ldloc.s  0x2A
0xa924b4  ldarg.1
0xa924b5  callvirt instance valuetype [mscorlib]System.Guid SPMigratableSite::get_ID()
0xa924ba  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass12::siteId
0xa924bf  ldarg.1
0xa924c0  callvirt instance string SPMigratableSite::get_Url()
0xa924c5  stloc.s  4
0xa924c7  ldnull
0xa924c8  stloc.s  5
0xa924ca  ldarg.1
0xa924cb  callvirt instance bool SPMigratableSite::get_Deleted()
0xa924d0  brtrue   loc_A92577
0xa924d5  ldloc.s  0x2A
0xa924d7  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass12::siteId
0xa924dc  ldarg.0
0xa924dd  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa924e2  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0xa924e7  call     class Microsoft.SharePoint.Administration.SPSiteLookupInfo Microsoft.SharePoint.SPSiteCache::LookupById(valuetype [mscorlib]System.Guid id, class Microsoft.SharePoint.Administration.SPFarm farm)
0xa924ec  stloc.s  5
0xa924ee  ldarg.2
0xa924ef  brtrue   loc_A92577
0xa924f4  ldloc.s  5
0xa924f6  brfalse.s loc_A92577
0xa924f8  ldloc.s  5
0xa924fa  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteLookupInfo::get_HostHeaderIsSiteName()
0xa924ff  brfalse.s loc_A92577
0xa92501  newobj   instance void <>c__DisplayClass14::.ctor()
0xa92506  stloc.s  7
0xa92508  ldloc.s  7
0xa9250a  ldloc.s  0x2A
0xa9250c  stfld    class <>c__DisplayClass12 <>c__DisplayClass14::CS$<>8__locals13
0xa92511  ldarg.0
0xa92512  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92517  callvirt instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0xa9251c  ldloc.s  0x2A
0xa9251e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass12::siteId
0xa92523  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPSiteUrl> Microsoft.SharePoint.Administration.SPConfigurationDatabase::GetUrlsForHostHeaderSite(valuetype [mscorlib]System.Guid siteId)
0xa92528  stloc.s  6
0xa9252a  ldloc.s  7
0xa9252c  ldarg.0
0xa9252d  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92532  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPContentDatabase::get_WebApplication()
0xa92537  ldloc.s  5
0xa92539  call     string Microsoft.SharePoint.SPHostHeaderSiteUri::GetSchemeStringFromSiteInfo(class Microsoft.SharePoint.Administration.SPWebApplication webApplication, class Microsoft.SharePoint.Administration.ISPSiteLookupInfo siteLookupInfo)
0xa9253e  ldsfld   string [System]System.Uri::SchemeDelimiter
0xa92543  ldloc.s  5
0xa92545  callvirt instance string Microsoft.SharePoint.Administration.SPSiteLookupInfo::get_Path()
0xa9254a  call     string [mscorlib]System.String::Concat(string, string, string)
0xa9254f  newobj   instance void [System]System.Uri::.ctor(string)
0xa92554  stfld    class [System]System.Uri <>c__DisplayClass14::primaryUri
0xa92559  ldloc.s  6
0xa9255b  ldloc.s  7
0xa9255d  ldftn    instance bool <>c__DisplayClass14::<CopyOrMoveSite>b__0(class Microsoft.SharePoint.SPSiteUrl spSiteUrl)
0xa92563  newobj   instance void class [mscorlib]System.Predicate`1<class Microsoft.SharePoint.SPSiteUrl>::.ctor(object, native int)
0xa92568  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPSiteUrl>::RemoveAll(class [mscorlib]System.Predicate`1<var<u1>>)
0xa9256d  pop
0xa9256e  ldloc.s  5
0xa92570  ldloc.s  6
0xa92572  callvirt instance void Microsoft.SharePoint.Administration.ISPSiteLookupInfo::set_SiteUrls(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.SPSiteUrl> value)
0xa92577  ldarg.1
0xa92578  callvirt instance class Microsoft.SharePoint.Utilities.SqlPartitionKey SPMigratableSite::get_PartitionKey()
0xa9257d  stloc.s  8
0xa9257f  ldarg.2
0xa92580  brfalse.s loc_A925A8
0xa92582  ldloc.s  0x2A
0xa92584  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass12::newSiteId
0xa92589  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xa9258e  brtrue.s loc_A925A8
0xa92590  ldloc.s  0x2A
0xa92592  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass12::newSiteId
0xa92597  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xa9259c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xa925a1  stobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xa925a6  br.s     loc_A925C3
0xa925a8  ldarg.2
0xa925a9  brtrue.s loc_A925C3
0xa925ab  ldloc.s  0x2A
0xa925ad  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass12::newSiteId
0xa925b2  ldloc.s  0x2A
0xa925b4  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass12::siteId
0xa925b9  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xa925be  stobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xa925c3  ldnull
0xa925c4  stloc.s  9
0xa925c6  ldarg.0
0xa925c7  ldfld    bool Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::m_copyingFromSiteMaster
0xa925cc  brfalse.s loc_A9263B
0xa925ce  ldnull
0xa925cf  stloc.s  0xA
0xa925d1  ldarg.0
0xa925d2  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa925d7  callvirt instance class [mscorlib]System.Version Microsoft.SharePoint.Administration.SPContentDatabase::get_SchemaVersion()
0xa925dc  callvirt instance string [mscorlib]System.Object::ToString()
0xa925e1  stloc.s  0xB
0xa925e3  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::s_SiteMasterSchemaCache
0xa925e8  ldloc.s  0xB
0xa925ea  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema>::ContainsKey(var<u1>)
0xa925ef  brfalse.s loc_A92601
0xa925f1  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::s_SiteMasterSchemaCache
0xa925f6  ldloc.s  0xB
0xa925f8  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema>::get_Item(void)
0xa925fd  stloc.s  0xA
0xa925ff  br.s     loc_A92625
0xa92601  ldarg.0
0xa92602  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92607  callvirt instance class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema Microsoft.SharePoint.Administration.SPContentDatabase::get_Schema()
0xa9260c  stloc.s  0xA
0xa9260e  ldarg.0
0xa9260f  ldloc.s  0xA
0xa92611  ldc.i4.1
0xa92612  call     instance void Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::UpdateSchemaBeforeCopy(class Microsoft.SharePoint.Utilities.Sql.SqlSchema coreSchema, bool bSiteMasterCopy)
0xa92617  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::s_SiteMasterSchemaCache
0xa9261c  ldloc.s  0xB
0xa9261e  ldloc.s  0xA
0xa92620  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.SPSqlSchema>::set_Item(var<u1>, !!T0)
0xa92625  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.SqlSchema>::.ctor()
0xa9262a  stloc.s  0xC
0xa9262c  ldloc.s  0xC
0xa9262e  ldloc.s  0xA
0xa92630  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.SqlSchema>::Add(var<u1>)
0xa92635  ldloc.s  0xC
0xa92637  stloc.s  9
0xa92639  br.s     loc_A92677
0xa9263b  ldarg.0
0xa9263c  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa92641  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Utilities.Sql.SqlSchema> Microsoft.SharePoint.Administration.SPContentDatabase::GetSchemasIncludingExtensions()
0xa92646  stloc.s  9
0xa92648  ldloc.s  9
0xa9264a  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Utilities.Sql.SqlSchema, bool> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CS$<>9__CachedAnonymousMethodDelegatea
0xa9264f  brtrue.s loc_A92662
0xa92651  ldnull
0xa92652  ldftn    bool Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::<CopyOrMoveSite>b__1(class Microsoft.SharePoint.Utilities.Sql.SqlSchema schema)
0xa92658  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.SharePoint.Utilities.Sql.SqlSchema, bool>::.ctor(object, native int)
0xa9265d  stsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Utilities.Sql.SqlSchema, bool> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CS$<>9__CachedAnonymousMethodDelegatea
0xa92662  ldsfld   class [mscorlib]System.Func`2<class Microsoft.SharePoint.Utilities.Sql.SqlSchema, bool> Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CS$<>9__CachedAnonymousMethodDelegatea
0xa92667  call     T0x2B000159
0xa9266c  stloc.s  0xD
0xa9266e  ldarg.0
0xa9266f  ldloc.s  0xD
0xa92671  ldc.i4.0
0xa92672  call     instance void Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::UpdateSchemaBeforeCopy(class Microsoft.SharePoint.Utilities.Sql.SqlSchema coreSchema, bool bSiteMasterCopy)
0xa92677  ldarg.0
0xa92678  ldloc.s  9
0xa9267a  ldloc.s  0x2A
0xa9267c  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass12::newSiteId
0xa92681  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xa92686  ldloc.s  0x2A
0xa92688  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass12::siteId
0xa9268d  ldloc.2
0xa9268e  ldloc.s  0x2A
0xa92690  ldfld    class Microsoft.SharePoint.SPSiteCopyParameters <>c__DisplayClass12::param
0xa92695  ldarg.2
0xa92696  call     instance class Microsoft.SharePoint.Utilities.Sql.SPSqlPartitionManager Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::CreatePartitionManager(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Utilities.Sql.SqlSchema> allSchemas, valuetype [mscorlib]System.Guid newSiteId, valuetype [mscorlib]System.Guid oldSiteId, bool bCreateDeleted, class Microsoft.SharePoint.SPSiteCopyParameters param, bool copy)
0xa9269b  stloc.s  0xE
0xa9269d  ldarg.0
0xa9269e  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_Log()
0xa926a3  ldc.i4   0x2588CD
0xa926a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa926ad  ldstr    a01_88// "{0} {1}."
0xa926b2  ldc.i4.2
0xa926b3  newarr   [mscorlib]System.Object
0xa926b8  stloc.s  0x2C
0xa926ba  ldloc.s  0x2C
0xa926bc  ldc.i4.0
0xa926bd  ldarg.2
0xa926be  brtrue.s loc_A926C7
0xa926c0  ldstr    aMoving// "Moving"
0xa926c5  br.s     loc_A926CC
0xa926c7  ldstr    aCopying// "Copying"
0xa926cc  stelem.ref
0xa926cd  ldloc.s  0x2C
0xa926cf  ldc.i4.1
0xa926d0  ldloc.s  4
0xa926d2  stelem.ref
0xa926d3  ldloc.s  0x2C
0xa926d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa926da  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa926df  ldc.i4.m1
0xa926e0  stloc.s  0xF
0xa926e2  ldloc.0
0xa926e3  brtrue.s loc_A92707
0xa926e5  ldarg.0
0xa926e6  ldfld    bool Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::m_copyingFromSiteMaster
0xa926eb  brtrue.s loc_A92707
0xa926ed  ldarg.1
0xa926ee  ldarg.0
0xa926ef  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_FromContentDatabase()
0xa926f4  ldarg.0
0xa926f5  call     instance valuetype Microsoft.SharePoint.Upgrade.SiteLockModifier Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_SourceSiteLockType()
0xa926fa  ldarg.0
0xa926fb  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_Log()
0xa92700  callvirt instance int32 SPMigratableSite::LockBeforeCopy(class Microsoft.SharePoint.Administration.SPContentDatabase db, valuetype Microsoft.SharePoint.Upgrade.SiteLockModifier lockSource, class Microsoft.SharePoint.Upgrade.SPLog log)
0xa92705  stloc.s  0xF
0xa92707  ldarg.2
0xa92708  brfalse.s loc_A92732
0xa9270a  ldarg.0
0xa9270b  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_ToContentDatabase()
0xa92710  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseExtensionCollection Microsoft.SharePoint.Administration.SPContentDatabase::get_DatabaseExtensions()
0xa92715  ldloc.s  0x23
0xa92717  brtrue.s loc_A92728
0xa92719  ldloc.s  0x2A
0xa9271b  ldftn    instance void <>c__DisplayClass12::<CopyOrMoveSite>b__2(class Microsoft.SharePoint.Administration.SPContentDatabaseExtension extension)
0xa92721  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.SharePoint.Administration.SPContentDatabaseExtension>::.ctor(object, native int)
0xa92726  stloc.s  0x23
0xa92728  ldloc.s  0x23
0xa9272a  ldc.i4.0
0xa9272b  callvirt instance void Microsoft.SharePoint.Administration.SPContentDatabaseExtensionCollection::ExecuteForAllExtensions(class [mscorlib]System.Action`1<class Microsoft.SharePoint.Administration.SPContentDatabaseExtension> action, [opt] bool noThrow)
0xa92730  br.s     loc_A92758
0xa92732  ldarg.0
0xa92733  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Upgrade.SPSiteCollectionCopier::get_ToContentDatabase()
0xa92738  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseExtensionCollection Microsoft.SharePoint.Administration.SPContentDatabase::get_DatabaseExtensions()
  ... truncated ...
```
