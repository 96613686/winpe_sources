# Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData

- ea: `0x38da80`
- end: `0x38dd4d`
- name: `Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::Microsoft.SharePoint.Administration.ISerializableUsageEntry.GetObjectData`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x7ae700`

## string_xrefs

- `0x38db53`: `ServiceCallCount`
- `0x38db3d`: `ServiceCallDuration`
- `0x38da97`: `RootWebTemplate`
- `0x38db7f`: `CreateFromSiteMaster`
- `0x38db95`: `BatchTableCopy`
- `0x38dbab`: `SiteCopyTimeMs`
- `0x38dbc1`: `SiteCopySqlQueryCount`
- `0x38dc03`: `RowCopyTimeMs`
- `0x38dc5b`: `ConfigDBCreateSiteMillisec`
- `0x38dc71`: `SpRequestCreateSiteMillisec`
- `0x38dc87`: `QuotaTemplateMillisec`
- `0x38dcc9`: `UpdateSiteSettingsMillisec`
- `0x38dcdf`: `UpdateRootWebPropertiesMillisec`
- `0x38dcf5`: `CopyFinalizationMillisec`
- `0x38dd0b`: `UpdateSiteSettingsUserInfoMillisec`
- `0x38dd21`: `UpdateSiteSettingsOwnerMillisec`
- `0x38dd37`: `UpdateSiteSettingsSubscriptionMillisec`

## pseudocode

```c

```

## disassembly

```asm
0x38da80  ldarg.1
0x38da81  ldstr    aSiteid_0// "SiteId"
0x38da86  ldarg.0
0x38da87  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteId
0x38da8c  box      [mscorlib]System.Guid
0x38da91  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38da96  ldarg.1
0x38da97  ldstr    aRootwebtemplat// "RootWebTemplate"
0x38da9c  ldarg.0
0x38da9d  ldfld    string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::rootWebTemplate
0x38daa2  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38daa7  ldarg.1
0x38daa8  ldstr    aCreationtimems// "CreationTimeMs"
0x38daad  ldarg.0
0x38daae  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::creationTimeMs
0x38dab3  box      [mscorlib]System.Int64
0x38dab8  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dabd  ldarg.1
0x38dabe  ldstr    aSqlquerycount// "SqlQueryCount"
0x38dac3  ldarg.0
0x38dac4  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlQueryCount
0x38dac9  box      [mscorlib]System.Int64
0x38dace  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dad3  ldarg.1
0x38dad4  ldstr    aSqlquerytime// "SqlQueryTime"
0x38dad9  ldarg.0
0x38dada  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlQueryTime
0x38dadf  box      [mscorlib]System.Int64
0x38dae4  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dae9  ldarg.1
0x38daea  ldstr    aSqlconnectiont// "SqlConnectionTime"
0x38daef  ldarg.0
0x38daf0  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::sqlConnectionTime
0x38daf5  box      [mscorlib]System.Int64
0x38dafa  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38daff  ldarg.1
0x38db00  ldstr    aSlowestqueryda// "SlowestQueryDatabase"
0x38db05  ldarg.0
0x38db06  ldfld    string Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::slowestQueryDatabase
0x38db0b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db10  ldarg.1
0x38db11  ldstr    aCpuduration// "CpuDuration"
0x38db16  ldarg.0
0x38db17  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::cpuDuration
0x38db1c  box      [mscorlib]System.Int64
0x38db21  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db26  ldarg.1
0x38db27  ldstr    aCpucycles// "CpuCycles"
0x38db2c  ldarg.0
0x38db2d  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::cpuCycles
0x38db32  box      [mscorlib]System.Int64
0x38db37  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db3c  ldarg.1
0x38db3d  ldstr    aServicecalldur_0// "ServiceCallDuration"
0x38db42  ldarg.0
0x38db43  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::serviceCallDuration
0x38db48  box      [mscorlib]System.Int64
0x38db4d  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db52  ldarg.1
0x38db53  ldstr    aServicecallcou// "ServiceCallCount"
0x38db58  ldarg.0
0x38db59  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::serviceCallCount
0x38db5e  box      [mscorlib]System.Int64
0x38db63  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db68  ldarg.1
0x38db69  ldstr    aCreatingsitema// "CreatingSiteMaster"
0x38db6e  ldarg.0
0x38db6f  ldfld    bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::creatingSiteMaster
0x38db74  box      [mscorlib]System.Boolean
0x38db79  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db7e  ldarg.1
0x38db7f  ldstr    aCreatefromsite// "CreateFromSiteMaster"
0x38db84  ldarg.0
0x38db85  ldfld    bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::createFromSiteMaster
0x38db8a  box      [mscorlib]System.Boolean
0x38db8f  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38db94  ldarg.1
0x38db95  ldstr    aBatchtablecopy// "BatchTableCopy"
0x38db9a  ldarg.0
0x38db9b  ldfld    bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::batchTableCopy
0x38dba0  box      [mscorlib]System.Boolean
0x38dba5  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dbaa  ldarg.1
0x38dbab  ldstr    aSitecopytimems// "SiteCopyTimeMs"
0x38dbb0  ldarg.0
0x38dbb1  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteCopyTimeMs
0x38dbb6  box      [mscorlib]System.Int64
0x38dbbb  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dbc0  ldarg.1
0x38dbc1  ldstr    aSitecopysqlque// "SiteCopySqlQueryCount"
0x38dbc6  ldarg.0
0x38dbc7  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteCopySqlQueryCount
0x38dbcc  box      [mscorlib]System.Int64
0x38dbd1  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dbd6  ldarg.1
0x38dbd7  ldstr    aFeatureactivat_6// "FeatureActivationTimeMs"
0x38dbdc  ldarg.0
0x38dbdd  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::featureActivationTimeMs
0x38dbe2  box      [mscorlib]System.Int64
0x38dbe7  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dbec  ldarg.1
0x38dbed  ldstr    aFeatureactivat_7// "FeatureActivationSqlQueryCount"
0x38dbf2  ldarg.0
0x38dbf3  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::featureActivationSqlQueryCount
0x38dbf8  box      [mscorlib]System.Int64
0x38dbfd  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc02  ldarg.1
0x38dc03  ldstr    aRowcopytimems// "RowCopyTimeMs"
0x38dc08  ldarg.0
0x38dc09  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::rowCopyTimeMs
0x38dc0e  box      [mscorlib]System.Int64
0x38dc13  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc18  ldarg.1
0x38dc19  ldstr    aSitedatabaseon// "SiteDatabaseOnSqlAzure"
0x38dc1e  ldarg.0
0x38dc1f  ldfld    bool Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteDatabaseOnSqlAzure
0x38dc24  box      [mscorlib]System.Boolean
0x38dc29  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc2e  ldarg.1
0x38dc2f  ldstr    aDatabasecheckm// "DatabaseCheckMillisec"
0x38dc34  ldarg.0
0x38dc35  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::databaseCheckMillisec
0x38dc3a  box      [mscorlib]System.Int64
0x38dc3f  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc44  ldarg.1
0x38dc45  ldstr    aSitemasterchec// "SiteMasterCheckMillisec"
0x38dc4a  ldarg.0
0x38dc4b  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::siteMasterCheckMillisec
0x38dc50  box      [mscorlib]System.Int64
0x38dc55  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc5a  ldarg.1
0x38dc5b  ldstr    aConfigdbcreate// "ConfigDBCreateSiteMillisec"
0x38dc60  ldarg.0
0x38dc61  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::configDBCreateSiteMillisec
0x38dc66  box      [mscorlib]System.Int64
0x38dc6b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc70  ldarg.1
0x38dc71  ldstr    aSprequestcreat// "SpRequestCreateSiteMillisec"
0x38dc76  ldarg.0
0x38dc77  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::spRequestCreateSiteMillisec
0x38dc7c  box      [mscorlib]System.Int64
0x38dc81  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc86  ldarg.1
0x38dc87  ldstr    aQuotatemplatem// "QuotaTemplateMillisec"
0x38dc8c  ldarg.0
0x38dc8d  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::quotaTemplateMillisec
0x38dc92  box      [mscorlib]System.Int64
0x38dc97  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dc9c  ldarg.1
0x38dc9d  ldstr    aNonsitemasterb// "NonSiteMasterBasedCreationMillisec"
0x38dca2  ldarg.0
0x38dca3  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::nonSiteMasterBasedCreationMillisec
0x38dca8  box      [mscorlib]System.Int64
0x38dcad  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dcb2  ldarg.1
0x38dcb3  ldstr    aEnsuresitemast// "EnsureSiteMasterMillisec"
0x38dcb8  ldarg.0
0x38dcb9  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::ensureSiteMasterMillisec
0x38dcbe  box      [mscorlib]System.Int64
0x38dcc3  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dcc8  ldarg.1
0x38dcc9  ldstr    aUpdatesitesett// "UpdateSiteSettingsMillisec"
0x38dcce  ldarg.0
0x38dccf  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsMillisec
0x38dcd4  box      [mscorlib]System.Int64
0x38dcd9  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dcde  ldarg.1
0x38dcdf  ldstr    aUpdaterootwebp_2// "UpdateRootWebPropertiesMillisec"
0x38dce4  ldarg.0
0x38dce5  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateRootWebPropertiesMillisec
0x38dcea  box      [mscorlib]System.Int64
0x38dcef  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dcf4  ldarg.1
0x38dcf5  ldstr    aCopyfinalizati// "CopyFinalizationMillisec"
0x38dcfa  ldarg.0
0x38dcfb  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::copyFinalizationMillisec
0x38dd00  box      [mscorlib]System.Int64
0x38dd05  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dd0a  ldarg.1
0x38dd0b  ldstr    aUpdatesitesett_0// "UpdateSiteSettingsUserInfoMillisec"
0x38dd10  ldarg.0
0x38dd11  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsUserInfoMillisec
0x38dd16  box      [mscorlib]System.Int64
0x38dd1b  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dd20  ldarg.1
0x38dd21  ldstr    aUpdatesitesett_1// "UpdateSiteSettingsOwnerMillisec"
0x38dd26  ldarg.0
0x38dd27  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsOwnerMillisec
0x38dd2c  box      [mscorlib]System.Int64
0x38dd31  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dd36  ldarg.1
0x38dd37  ldstr    aUpdatesitesett_2// "UpdateSiteSettingsSubscriptionMillisec"
0x38dd3c  ldarg.0
0x38dd3d  ldfld    int64 Microsoft.SharePoint.Administration.SPSiteCreationUsageEntry::updateSiteSettingsSubscriptionMillisec
0x38dd42  box      [mscorlib]System.Int64
0x38dd47  callvirt instance void Microsoft.SharePoint.Utilities.SPKeyValuePairSerializationInfo::AddValue(string name, object value)
0x38dd4c  ret
```
