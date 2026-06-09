# Microsoft.SharePoint.Administration.SPConfigurationDatabase::.cctor

- ea: `0x24fa10`
- end: `0x24fd7d`
- name: `Microsoft.SharePoint.Administration.SPConfigurationDatabase::.cctor`
- size: `877`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x23cb80`

## string_xrefs

- `0x24fc5f`: `proc_createNewAppSiteDomainIds`
- `0x24fbfc`: `proc_deleteCacheConfigEntries`
- `0x24fbf3`: `proc_deleteCacheConfigEntry`
- `0x24fc83`: `proc_DeleteExtensionMap`
- `0x24fc8c`: `proc_GetAllExtensionMap`
- `0x24fc32`: `proc_getCacheClusterConfigSchemaVersion`
- `0x24fc17`: `proc_getCacheClusterConfigUtcTime`
- `0x24fc0e`: `proc_getCacheConfigEntries`
- `0x24fc05`: `proc_getCacheConfigEntry`
- `0x24fc20`: `proc_getCacheConfigEntry`
- `0x24fcb9`: `proc_GetDefaultExtensionDataHost`
- `0x24faca`: `proc_getDeletedSite`
- `0x24fab8`: `proc_getDeletedSitesByQuery`
- `0x24fac1`: `proc_getDeletedSitesBySiteId`
- `0x24faaf`: `proc_getDeletedSitesByUrl`
- `0x24fc95`: `proc_GetExtensionMap`
- `0x24fce6`: `proc_getSiteCountBySubscriptionIdAndPathPrefix`
- `0x24fb63`: `proc_gettemplate`
- `0x24fc29`: `proc_insertCacheConfigEntry`
- `0x24fa8f`: `proc_putDeletedSiteMap`
- `0x24fb87`: `proc_putDistributionListToDelete`
- `0x24fca7`: `proc_ResetExtensionMap`
- `0x24fcf8`: `proc_ResetExtensionMapV2`
- `0x24fcb0`: `proc_RestoreExtensionMap`
- `0x24fc9e`: `proc_SetExtensionMap`
- `0x24fcef`: `proc_SetExtensionMapV2`
- `0x24fc3b`: `proc_updateCacheConfigEntry`
- `0x24fa10`: `cache.ini`
- `0x24fa5b`: `IN_REFRESH_CACHE`

## pseudocode

```c

```

## disassembly

```asm
0x24fa10  ldstr    aCacheIni// "cache.ini"
0x24fa15  stsfld   string Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_CacheIniFile
0x24fa1a  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::.ctor()
0x24fa1f  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_ObjectsInNativeConfigurationCache
0x24fa24  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_mainProcessModuleValidated
0x24fa29  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x24fa2f  ldc.i4.0
0x24fa30  stsfld   bool Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_InDatabaseProvision
0x24fa35  ldc.i4.0
0x24fa36  stsfld   bool Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_EverMadeChangesInThisProcess
0x24fa3b  ldc.i4.0
0x24fa3c  stsfld   bool Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_FailedLastRefreshInThisProcess
0x24fa41  ldc.i4.1
0x24fa42  stsfld   bool Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_AllowDerivedCollectionCacheBuild
0x24fa47  newobj   instance void Microsoft.SharePoint.Administration.SPCachePerformanceProvider::.ctor()
0x24fa4c  stsfld   class Microsoft.SharePoint.Administration.SPCachePerformanceProvider Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_ObjectCacheProvider
0x24fa51  newobj   instance void Microsoft.SharePoint.Administration.SPCachePerformanceProvider::.ctor()
0x24fa56  stsfld   class Microsoft.SharePoint.Administration.SPCachePerformanceProvider Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_NameCacheProvider
0x24fa5b  ldstr    aInRefreshCache// "IN_REFRESH_CACHE"
0x24fa60  stsfld   string Microsoft.SharePoint.Administration.SPConfigurationDatabase::s_RecursionTestString
0x24fa65  ldc.i4.s 0x4A
0x24fa67  newarr   [mscorlib]System.String
0x24fa6c  stloc.0
0x24fa6d  ldloc.0
0x24fa6e  ldc.i4.0
0x24fa6f  ldstr    aProcDropemaile// "proc_dropEmailEnabledList"
0x24fa74  stelem.ref
0x24fa75  ldloc.0
0x24fa76  ldc.i4.1
0x24fa77  ldstr    aProcDropemaile_1// "proc_dropEmailEnabledListsByWeb"
0x24fa7c  stelem.ref
0x24fa7d  ldloc.0
0x24fa7e  ldc.i4.2
0x24fa7f  ldstr    aProcDroppendin// "proc_dropPendingDistributionList"
0x24fa84  stelem.ref
0x24fa85  ldloc.0
0x24fa86  ldc.i4.3
0x24fa87  ldstr    aProcDropsitema// "proc_dropSiteMap"
0x24fa8c  stelem.ref
0x24fa8d  ldloc.0
0x24fa8e  ldc.i4.4
0x24fa8f  ldstr    aProcPutdeleted// "proc_putDeletedSiteMap"
0x24fa94  stelem.ref
0x24fa95  ldloc.0
0x24fa96  ldc.i4.5
0x24fa97  ldstr    aProcDropsitema_0// "proc_dropSiteMap2"
0x24fa9c  stelem.ref
0x24fa9d  ldloc.0
0x24fa9e  ldc.i4.6
0x24fa9f  ldstr    aProcHidesitema// "proc_hideSiteMap"
0x24faa4  stelem.ref
0x24faa5  ldloc.0
0x24faa6  ldc.i4.7
0x24faa7  ldstr    aProcUnhidesite// "proc_unhideSiteMap"
0x24faac  stelem.ref
0x24faad  ldloc.0
0x24faae  ldc.i4.8
0x24faaf  ldstr    aProcGetdeleted_3// "proc_getDeletedSitesByUrl"
0x24fab4  stelem.ref
0x24fab5  ldloc.0
0x24fab6  ldc.i4.s 9
0x24fab8  ldstr    aProcGetdeleted_1// "proc_getDeletedSitesByQuery"
0x24fabd  stelem.ref
0x24fabe  ldloc.0
0x24fabf  ldc.i4.s 0xA
0x24fac1  ldstr    aProcGetdeleted_2// "proc_getDeletedSitesBySiteId"
0x24fac6  stelem.ref
0x24fac7  ldloc.0
0x24fac8  ldc.i4.s 0xB
0x24faca  ldstr    aProcGetdeleted_0// "proc_getDeletedSite"
0x24facf  stelem.ref
0x24fad0  ldloc.0
0x24fad1  ldc.i4.s 0xC
0x24fad3  ldstr    aProcGetdepende// "proc_getDependentObjectsByBaseClass"
0x24fad8  stelem.ref
0x24fad9  ldloc.0
0x24fada  ldc.i4.s 0xD
0x24fadc  ldstr    aProcGetdepende_0// "proc_getDependentObjectsByBaseClass_CTE"
0x24fae1  stelem.ref
0x24fae2  ldloc.0
0x24fae3  ldc.i4.s 0xE
0x24fae5  ldstr    aProcGetemailen// "proc_getEmailEnabledListByAlias"
0x24faea  stelem.ref
0x24faeb  ldloc.0
0x24faec  ldc.i4.s 0xF
0x24faee  ldstr    aProcGetobjects// "proc_getObjectsByBaseClass"
0x24faf3  stelem.ref
0x24faf4  ldloc.0
0x24faf5  ldc.i4.s 0x10
0x24faf7  ldstr    aProcGetobjects_0// "proc_getObjectsByBaseClass_CTE"
0x24fafc  stelem.ref
0x24fafd  ldloc.0
0x24fafe  ldc.i4.s 0x11
0x24fb00  ldstr    aProcGetobjects_1// "proc_getObjectsByClass"
0x24fb05  stelem.ref
0x24fb06  ldloc.0
0x24fb07  ldc.i4.s 0x12
0x24fb09  ldstr    aProcGetfile// "proc_getFile"
0x24fb0e  stelem.ref
0x24fb0f  ldloc.0
0x24fb10  ldc.i4.s 0x13
0x24fb12  ldstr    aProcGetsitecou// "proc_getSiteCount"
0x24fb17  stelem.ref
0x24fb18  ldloc.0
0x24fb19  ldc.i4.s 0x14
0x24fb1b  ldstr    aProcGetsiteinf_0// "proc_GetSiteInfoFromAppSiteDomainPrefix"
0x24fb20  stelem.ref
0x24fb21  ldloc.0
0x24fb22  ldc.i4.s 0x15
0x24fb24  ldstr    aProcGetsiteinf_1// "proc_getSiteInfoOfHostHeaderSite"
0x24fb29  stelem.ref
0x24fb2a  ldloc.0
0x24fb2b  ldc.i4.s 0x16
0x24fb2d  ldstr    aProcGetsiteids// "proc_getSiteIds"
0x24fb32  stelem.ref
0x24fb33  ldloc.0
0x24fb34  ldc.i4.s 0x17
0x24fb36  ldstr    aProcGetsiteida// "proc_getSiteIdAndZoneOfHostHeaderSite"
0x24fb3b  stelem.ref
0x24fb3c  ldloc.0
0x24fb3d  ldc.i4.s 0x18
0x24fb3f  ldstr    aProcGetsitemap// "proc_getSiteMap"
0x24fb44  stelem.ref
0x24fb45  ldloc.0
0x24fb46  ldc.i4.s 0x19
0x24fb48  ldstr    aProcGetsitemap_0// "proc_getSiteMapById"
0x24fb4d  stelem.ref
0x24fb4e  ldloc.0
0x24fb4f  ldc.i4.s 0x1A
0x24fb51  ldstr    aProcGetsitenam// "proc_getSiteNames"
0x24fb56  stelem.ref
0x24fb57  ldloc.0
0x24fb58  ldc.i4.s 0x1B
0x24fb5a  ldstr    aProcGetsubscri// "proc_getSubscriptionIds"
0x24fb5f  stelem.ref
0x24fb60  ldloc.0
0x24fb61  ldc.i4.s 0x1C
0x24fb63  ldstr    aProcGettemplat// "proc_gettemplate"
0x24fb68  stelem.ref
0x24fb69  ldloc.0
0x24fb6a  ldc.i4.s 0x1D
0x24fb6c  ldstr    aProcMarkfordel// "proc_markForDeletionEmailEnabledList"
0x24fb71  stelem.ref
0x24fb72  ldloc.0
0x24fb73  ldc.i4.s 0x1E
0x24fb75  ldstr    aProcMarkfordel_0// "proc_markForDeletionEmailEnabledListsBy"...
0x24fb7a  stelem.ref
0x24fb7b  ldloc.0
0x24fb7c  ldc.i4.s 0x1F
0x24fb7e  ldstr    aProcMarkfordel_1// "proc_markForDeletionEmailEnabledListsBy"...
0x24fb83  stelem.ref
0x24fb84  ldloc.0
0x24fb85  ldc.i4.s 0x20
0x24fb87  ldstr    aProcPutdistrib// "proc_putDistributionListToDelete"
0x24fb8c  stelem.ref
0x24fb8d  ldloc.0
0x24fb8e  ldc.i4.s 0x21
0x24fb90  ldstr    aProcPutemailen// "proc_putEmailEnabledList"
0x24fb95  stelem.ref
0x24fb96  ldloc.0
0x24fb97  ldc.i4.s 0x22
0x24fb99  ldstr    aProcPutpending// "proc_putPendingDistributionList"
0x24fb9e  stelem.ref
0x24fb9f  ldloc.0
0x24fba0  ldc.i4.s 0x23
0x24fba2  ldstr    aProcPutsitemap// "proc_putSiteMap"
0x24fba7  stelem.ref
0x24fba8  ldloc.0
0x24fba9  ldc.i4.s 0x24
0x24fbab  ldstr    aProcGetobject// "proc_getObject"
0x24fbb0  stelem.ref
0x24fbb1  ldloc.0
0x24fbb2  ldc.i4.s 0x25
0x24fbb4  ldstr    aProcSetsubscri// "proc_setSubscription"
0x24fbb9  stelem.ref
0x24fbba  ldloc.0
0x24fbbb  ldc.i4.s 0x26
0x24fbbd  ldstr    aProcSetsources// "proc_setSourceSiteId"
0x24fbc2  stelem.ref
0x24fbc3  ldloc.0
0x24fbc4  ldc.i4.s 0x27
0x24fbc6  ldstr    aProcGetevalsit// "proc_getEvalSites"
0x24fbcb  stelem.ref
0x24fbcc  ldloc.0
0x24fbcd  ldc.i4.s 0x28
0x24fbcf  ldstr    aProcSetappsite// "proc_SetAppSiteDomainPrefix"
0x24fbd4  stelem.ref
0x24fbd5  ldloc.0
0x24fbd6  ldc.i4.s 0x29
0x24fbd8  ldstr    aProcAddurltosi// "proc_addUrlToSite"
0x24fbdd  stelem.ref
0x24fbde  ldloc.0
0x24fbdf  ldc.i4.s 0x2A
0x24fbe1  ldstr    aProcSetzonefor// "proc_setZoneForUrl"
0x24fbe6  stelem.ref
0x24fbe7  ldloc.0
0x24fbe8  ldc.i4.s 0x2B
0x24fbea  ldstr    aProcGeturlsfor// "proc_getUrlsForSite"
0x24fbef  stelem.ref
0x24fbf0  ldloc.0
0x24fbf1  ldc.i4.s 0x2C
0x24fbf3  ldstr    aProcDeletecach_0// "proc_deleteCacheConfigEntry"
0x24fbf8  stelem.ref
0x24fbf9  ldloc.0
0x24fbfa  ldc.i4.s 0x2D
0x24fbfc  ldstr    aProcDeletecach// "proc_deleteCacheConfigEntries"
0x24fc01  stelem.ref
0x24fc02  ldloc.0
0x24fc03  ldc.i4.s 0x2E
0x24fc05  ldstr    aProcGetcacheco_0// "proc_getCacheConfigEntry"
0x24fc0a  stelem.ref
0x24fc0b  ldloc.0
0x24fc0c  ldc.i4.s 0x2F
0x24fc0e  ldstr    aProcGetcacheco// "proc_getCacheConfigEntries"
0x24fc13  stelem.ref
0x24fc14  ldloc.0
0x24fc15  ldc.i4.s 0x30
0x24fc17  ldstr    aProcGetcachecl_0// "proc_getCacheClusterConfigUtcTime"
0x24fc1c  stelem.ref
0x24fc1d  ldloc.0
0x24fc1e  ldc.i4.s 0x31
0x24fc20  ldstr    aProcGetcacheco_0// "proc_getCacheConfigEntry"
0x24fc25  stelem.ref
0x24fc26  ldloc.0
0x24fc27  ldc.i4.s 0x32
0x24fc29  ldstr    aProcInsertcach// "proc_insertCacheConfigEntry"
0x24fc2e  stelem.ref
0x24fc2f  ldloc.0
0x24fc30  ldc.i4.s 0x33
0x24fc32  ldstr    aProcGetcachecl// "proc_getCacheClusterConfigSchemaVersion"
0x24fc37  stelem.ref
0x24fc38  ldloc.0
0x24fc39  ldc.i4.s 0x34
0x24fc3b  ldstr    aProcUpdatecach// "proc_updateCacheConfigEntry"
0x24fc40  stelem.ref
0x24fc41  ldloc.0
0x24fc42  ldc.i4.s 0x35
0x24fc44  ldstr    aProcSetsubscri_0// "proc_setSubscriptionName"
0x24fc49  stelem.ref
0x24fc4a  ldloc.0
0x24fc4b  ldc.i4.s 0x36
0x24fc4d  ldstr    aProcGetcontent_0// "proc_getContentDatabaseIdsWithSubscript"...
0x24fc52  stelem.ref
0x24fc53  ldloc.0
0x24fc54  ldc.i4.s 0x37
0x24fc56  ldstr    aProcGetcontent// "proc_getContentDatabaseIds"
0x24fc5b  stelem.ref
0x24fc5c  ldloc.0
0x24fc5d  ldc.i4.s 0x38
0x24fc5f  ldstr    aProcCreatenewa_0// "proc_createNewAppSiteDomainIds"
0x24fc64  stelem.ref
0x24fc65  ldloc.0
0x24fc66  ldc.i4.s 0x39
0x24fc68  ldstr    aProcGetsitesub_0// "proc_getSiteSubscriptionsInWebApplicati"...
0x24fc6d  stelem.ref
0x24fc6e  ldloc.0
0x24fc6f  ldc.i4.s 0x3A
0x24fc71  ldstr    aProcGetsiteinf// "proc_getSiteInfoDatabases"
0x24fc76  stelem.ref
0x24fc77  ldloc.0
0x24fc78  ldc.i4.s 0x3B
0x24fc7a  ldstr    aProcGetdiskuse// "proc_getDiskUsedDatabases"
0x24fc7f  stelem.ref
0x24fc80  ldloc.0
0x24fc81  ldc.i4.s 0x3C
0x24fc83  ldstr    aProcDeleteexte// "proc_DeleteExtensionMap"
0x24fc88  stelem.ref
0x24fc89  ldloc.0
0x24fc8a  ldc.i4.s 0x3D
0x24fc8c  ldstr    aProcGetallexte// "proc_GetAllExtensionMap"
0x24fc91  stelem.ref
0x24fc92  ldloc.0
0x24fc93  ldc.i4.s 0x3E
0x24fc95  ldstr    aProcGetextensi// "proc_GetExtensionMap"
0x24fc9a  stelem.ref
0x24fc9b  ldloc.0
0x24fc9c  ldc.i4.s 0x3F
0x24fc9e  ldstr    aProcSetextensi// "proc_SetExtensionMap"
0x24fca3  stelem.ref
0x24fca4  ldloc.0
0x24fca5  ldc.i4.s 0x40
0x24fca7  ldstr    aProcResetexten// "proc_ResetExtensionMap"
0x24fcac  stelem.ref
0x24fcad  ldloc.0
0x24fcae  ldc.i4.s 0x41
0x24fcb0  ldstr    aProcRestoreext// "proc_RestoreExtensionMap"
0x24fcb5  stelem.ref
0x24fcb6  ldloc.0
0x24fcb7  ldc.i4.s 0x42
0x24fcb9  ldstr    aProcGetdefault// "proc_GetDefaultExtensionDataHost"
0x24fcbe  stelem.ref
0x24fcbf  ldloc.0
0x24fcc0  ldc.i4.s 0x43
0x24fcc2  ldstr    aProcGetsitesub// "proc_getSiteSubscriptionsInContentDB"
0x24fcc7  stelem.ref
0x24fcc8  ldloc.0
0x24fcc9  ldc.i4.s 0x44
0x24fccb  ldstr    aProcChecksubsc_0// "proc_checkSubscriptionIdExistsInFarm"
0x24fcd0  stelem.ref
0x24fcd1  ldloc.0
  ... truncated ...
```
