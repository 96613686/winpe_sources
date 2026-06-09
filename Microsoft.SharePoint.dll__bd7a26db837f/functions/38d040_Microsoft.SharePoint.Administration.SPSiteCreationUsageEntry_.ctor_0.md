# Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::.ctor_0

- ea: `0x38d040`
- end: `0x38d2bb`
- name: `Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::.ctor_0`
- size: `635`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2060c0`

## string_xrefs

- `0x38d11d`: `ServiceCallCount`
- `0x38d10b`: `ServiceCallDuration`
- `0x38d07b`: `RootWebTemplate`
- `0x38d141`: `CreateFromSiteMaster`
- `0x38d153`: `BatchTableCopy`
- `0x38d165`: `SiteCopyTimeMs`
- `0x38d177`: `SiteCopySqlQueryCount`
- `0x38d1ad`: `RowCopyTimeMs`
- `0x38d1f5`: `ConfigDBCreateSiteMillisec`
- `0x38d207`: `SpRequestCreateSiteMillisec`
- `0x38d219`: `QuotaTemplateMillisec`
- `0x38d24f`: `UpdateSiteSettingsMillisec`
- `0x38d261`: `UpdateRootWebPropertiesMillisec`
- `0x38d273`: `CopyFinalizationMillisec`
- `0x38d285`: `UpdateSiteSettingsUserInfoMillisec`
- `0x38d297`: `UpdateSiteSettingsOwnerMillisec`
- `0x38d2a9`: `UpdateSiteSettingsSubscriptionMillisec`

## pseudocode

```c

```

## disassembly

```asm
0x38d040  ldarg.0
0x38d041  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38d046  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteId
0x38d04b  ldarg.0
0x38d04c  ldsfld   string [mscorlib]System.String::Empty
0x38d051  stfld    string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::rootWebTemplate
0x38d056  ldarg.0
0x38d057  ldsfld   string [mscorlib]System.String::Empty
0x38d05c  stfld    string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::slowestQueryDatabase
0x38d061  ldarg.0
0x38d062  ldarg.1
0x38d063  call     instance void Microsoft.SharePoint.Administration.SPUsageEntry::.ctor(class Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo info)
0x38d068  ldarg.1
0x38d069  ldstr    aSiteid_0// "SiteId"
0x38d06e  ldarg.0
0x38d06f  ldflda   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteId
0x38d074  callvirt T0x2B0000FC
0x38d079  pop
0x38d07a  ldarg.1
0x38d07b  ldstr    aRootwebtemplat// "RootWebTemplate"
0x38d080  ldarg.0
0x38d081  ldflda   string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::rootWebTemplate
0x38d086  callvirt T0x2B0000FD
0x38d08b  pop
0x38d08c  ldarg.1
0x38d08d  ldstr    aCreationtimems// "CreationTimeMs"
0x38d092  ldarg.0
0x38d093  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::creationTimeMs
0x38d098  callvirt T0x2B000271
0x38d09d  pop
0x38d09e  ldarg.1
0x38d09f  ldstr    aSqlquerycount// "SqlQueryCount"
0x38d0a4  ldarg.0
0x38d0a5  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlQueryCount
0x38d0aa  callvirt T0x2B000271
0x38d0af  pop
0x38d0b0  ldarg.1
0x38d0b1  ldstr    aSqlquerytime// "SqlQueryTime"
0x38d0b6  ldarg.0
0x38d0b7  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlQueryTime
0x38d0bc  callvirt T0x2B000271
0x38d0c1  pop
0x38d0c2  ldarg.1
0x38d0c3  ldstr    aSqlconnectiont// "SqlConnectionTime"
0x38d0c8  ldarg.0
0x38d0c9  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlConnectionTime
0x38d0ce  callvirt T0x2B000271
0x38d0d3  pop
0x38d0d4  ldarg.1
0x38d0d5  ldstr    aSlowestqueryda// "SlowestQueryDatabase"
0x38d0da  ldarg.0
0x38d0db  ldflda   string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::slowestQueryDatabase
0x38d0e0  callvirt T0x2B0000FD
0x38d0e5  pop
0x38d0e6  ldarg.1
0x38d0e7  ldstr    aCpuduration// "CpuDuration"
0x38d0ec  ldarg.0
0x38d0ed  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::cpuDuration
0x38d0f2  callvirt T0x2B000271
0x38d0f7  pop
0x38d0f8  ldarg.1
0x38d0f9  ldstr    aCpucycles// "CpuCycles"
0x38d0fe  ldarg.0
0x38d0ff  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::cpuCycles
0x38d104  callvirt T0x2B000271
0x38d109  pop
0x38d10a  ldarg.1
0x38d10b  ldstr    aServicecalldur_0// "ServiceCallDuration"
0x38d110  ldarg.0
0x38d111  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::serviceCallDuration
0x38d116  callvirt T0x2B000271
0x38d11b  pop
0x38d11c  ldarg.1
0x38d11d  ldstr    aServicecallcou// "ServiceCallCount"
0x38d122  ldarg.0
0x38d123  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::serviceCallCount
0x38d128  callvirt T0x2B000271
0x38d12d  pop
0x38d12e  ldarg.1
0x38d12f  ldstr    aCreatingsitema// "CreatingSiteMaster"
0x38d134  ldarg.0
0x38d135  ldflda   bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::creatingSiteMaster
0x38d13a  callvirt T0x2B000272
0x38d13f  pop
0x38d140  ldarg.1
0x38d141  ldstr    aCreatefromsite// "CreateFromSiteMaster"
0x38d146  ldarg.0
0x38d147  ldflda   bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::createFromSiteMaster
0x38d14c  callvirt T0x2B000272
0x38d151  pop
0x38d152  ldarg.1
0x38d153  ldstr    aBatchtablecopy// "BatchTableCopy"
0x38d158  ldarg.0
0x38d159  ldflda   bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::batchTableCopy
0x38d15e  callvirt T0x2B000272
0x38d163  pop
0x38d164  ldarg.1
0x38d165  ldstr    aSitecopytimems// "SiteCopyTimeMs"
0x38d16a  ldarg.0
0x38d16b  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteCopyTimeMs
0x38d170  callvirt T0x2B000271
0x38d175  pop
0x38d176  ldarg.1
0x38d177  ldstr    aSitecopysqlque// "SiteCopySqlQueryCount"
0x38d17c  ldarg.0
0x38d17d  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteCopySqlQueryCount
0x38d182  callvirt T0x2B000271
0x38d187  pop
0x38d188  ldarg.1
0x38d189  ldstr    aFeatureactivat_6// "FeatureActivationTimeMs"
0x38d18e  ldarg.0
0x38d18f  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::featureActivationTimeMs
0x38d194  callvirt T0x2B000271
0x38d199  pop
0x38d19a  ldarg.1
0x38d19b  ldstr    aFeatureactivat_7// "FeatureActivationSqlQueryCount"
0x38d1a0  ldarg.0
0x38d1a1  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::featureActivationSqlQueryCount
0x38d1a6  callvirt T0x2B000271
0x38d1ab  pop
0x38d1ac  ldarg.1
0x38d1ad  ldstr    aRowcopytimems// "RowCopyTimeMs"
0x38d1b2  ldarg.0
0x38d1b3  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::rowCopyTimeMs
0x38d1b8  callvirt T0x2B000271
0x38d1bd  pop
0x38d1be  ldarg.1
0x38d1bf  ldstr    aSitedatabaseon// "SiteDatabaseOnSqlAzure"
0x38d1c4  ldarg.0
0x38d1c5  ldflda   bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteDatabaseOnSqlAzure
0x38d1ca  callvirt T0x2B000272
0x38d1cf  pop
0x38d1d0  ldarg.1
0x38d1d1  ldstr    aDatabasecheckm// "DatabaseCheckMillisec"
0x38d1d6  ldarg.0
0x38d1d7  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::databaseCheckMillisec
0x38d1dc  callvirt T0x2B000271
0x38d1e1  pop
0x38d1e2  ldarg.1
0x38d1e3  ldstr    aSitemasterchec// "SiteMasterCheckMillisec"
0x38d1e8  ldarg.0
0x38d1e9  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteMasterCheckMillisec
0x38d1ee  callvirt T0x2B000271
0x38d1f3  pop
0x38d1f4  ldarg.1
0x38d1f5  ldstr    aConfigdbcreate// "ConfigDBCreateSiteMillisec"
0x38d1fa  ldarg.0
0x38d1fb  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::configDBCreateSiteMillisec
0x38d200  callvirt T0x2B000271
0x38d205  pop
0x38d206  ldarg.1
0x38d207  ldstr    aSprequestcreat// "SpRequestCreateSiteMillisec"
0x38d20c  ldarg.0
0x38d20d  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::spRequestCreateSiteMillisec
0x38d212  callvirt T0x2B000271
0x38d217  pop
0x38d218  ldarg.1
0x38d219  ldstr    aQuotatemplatem// "QuotaTemplateMillisec"
0x38d21e  ldarg.0
0x38d21f  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::quotaTemplateMillisec
0x38d224  callvirt T0x2B000271
0x38d229  pop
0x38d22a  ldarg.1
0x38d22b  ldstr    aNonsitemasterb// "NonSiteMasterBasedCreationMillisec"
0x38d230  ldarg.0
0x38d231  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::nonSiteMasterBasedCreationMillisec
0x38d236  callvirt T0x2B000271
0x38d23b  pop
0x38d23c  ldarg.1
0x38d23d  ldstr    aEnsuresitemast// "EnsureSiteMasterMillisec"
0x38d242  ldarg.0
0x38d243  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::ensureSiteMasterMillisec
0x38d248  callvirt T0x2B000271
0x38d24d  pop
0x38d24e  ldarg.1
0x38d24f  ldstr    aUpdatesitesett// "UpdateSiteSettingsMillisec"
0x38d254  ldarg.0
0x38d255  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsMillisec
0x38d25a  callvirt T0x2B000271
0x38d25f  pop
0x38d260  ldarg.1
0x38d261  ldstr    aUpdaterootwebp_2// "UpdateRootWebPropertiesMillisec"
0x38d266  ldarg.0
0x38d267  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateRootWebPropertiesMillisec
0x38d26c  callvirt T0x2B000271
0x38d271  pop
0x38d272  ldarg.1
0x38d273  ldstr    aCopyfinalizati// "CopyFinalizationMillisec"
0x38d278  ldarg.0
0x38d279  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::copyFinalizationMillisec
0x38d27e  callvirt T0x2B000271
0x38d283  pop
0x38d284  ldarg.1
0x38d285  ldstr    aUpdatesitesett_0// "UpdateSiteSettingsUserInfoMillisec"
0x38d28a  ldarg.0
0x38d28b  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsUserInfoMillisec
0x38d290  callvirt T0x2B000271
0x38d295  pop
0x38d296  ldarg.1
0x38d297  ldstr    aUpdatesitesett_1// "UpdateSiteSettingsOwnerMillisec"
0x38d29c  ldarg.0
0x38d29d  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsOwnerMillisec
0x38d2a2  callvirt T0x2B000271
0x38d2a7  pop
0x38d2a8  ldarg.1
0x38d2a9  ldstr    aUpdatesitesett_2// "UpdateSiteSettingsSubscriptionMillisec"
0x38d2ae  ldarg.0
0x38d2af  ldflda   int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsSubscriptionMillisec
0x38d2b4  callvirt T0x2B000271
0x38d2b9  pop
0x38d2ba  ret
```
