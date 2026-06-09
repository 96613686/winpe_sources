# Microsoft.SharePoint.Administration.SPSiteCreationUsageProvider::<.ctor>b__2

- ea: `0x38cd70`
- end: `0x38cfb7`
- name: `Microsoft.SharePoint.Administration.SPSiteCreationUsageProvider::<.ctor>b__2`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x378200`
- `0x378210`

## string_xrefs

- `0x38ce2f`: `ServiceCallCount`
- `0x38ce1e`: `ServiceCallDuration`
- `0x38cd8a`: `RootWebTemplate`
- `0x38ce51`: `CreateFromSiteMaster`
- `0x38ce62`: `BatchTableCopy`
- `0x38ce73`: `SiteCopyTimeMs`
- `0x38ce84`: `SiteCopySqlQueryCount`
- `0x38ceb7`: `RowCopyTimeMs`
- `0x38cefb`: `ConfigDBCreateSiteMillisec`
- `0x38cf0c`: `SpRequestCreateSiteMillisec`
- `0x38cf1d`: `QuotaTemplateMillisec`
- `0x38cf50`: `UpdateSiteSettingsMillisec`
- `0x38cf61`: `UpdateRootWebPropertiesMillisec`
- `0x38cf72`: `CopyFinalizationMillisec`
- `0x38cf83`: `UpdateSiteSettingsUserInfoMillisec`
- `0x38cf94`: `UpdateSiteSettingsOwnerMillisec`
- `0x38cfa5`: `UpdateSiteSettingsSubscriptionMillisec`

## pseudocode

```c

```

## disassembly

```asm
0x38cd70  ldc.i4.1
0x38cd71  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::.ctor(int32)
0x38cd76  stloc.0
0x38cd77  ldloc.0
0x38cd78  ldstr    aSiteid_0// "SiteId"
0x38cd7d  ldc.i4.s 0xE
0x38cd7f  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd84  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd89  ldloc.0
0x38cd8a  ldstr    aRootwebtemplat// "RootWebTemplate"
0x38cd8f  ldc.i4.s 0xC
0x38cd91  ldc.i4   0x80
0x38cd96  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38cd9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cda0  ldloc.0
0x38cda1  ldstr    aCreationtimems// "CreationTimeMs"
0x38cda6  ldc.i4.0
0x38cda7  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cdac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cdb1  ldloc.0
0x38cdb2  ldstr    aSqlquerycount// "SqlQueryCount"
0x38cdb7  ldc.i4.0
0x38cdb8  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cdbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cdc2  ldloc.0
0x38cdc3  ldstr    aSqlquerytime// "SqlQueryTime"
0x38cdc8  ldc.i4.0
0x38cdc9  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cdce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cdd3  ldloc.0
0x38cdd4  ldstr    aSqlconnectiont// "SqlConnectionTime"
0x38cdd9  ldc.i4.0
0x38cdda  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cddf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cde4  ldloc.0
0x38cde5  ldstr    aSlowestqueryda// "SlowestQueryDatabase"
0x38cdea  ldc.i4.s 0xC
0x38cdec  ldc.i4   0x80
0x38cdf1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38cdf6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cdfb  ldloc.0
0x38cdfc  ldstr    aCpuduration// "CpuDuration"
0x38ce01  ldc.i4.0
0x38ce02  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce0c  ldloc.0
0x38ce0d  ldstr    aCpucycles// "CpuCycles"
0x38ce12  ldc.i4.0
0x38ce13  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce1d  ldloc.0
0x38ce1e  ldstr    aServicecalldur_0// "ServiceCallDuration"
0x38ce23  ldc.i4.0
0x38ce24  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce29  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce2e  ldloc.0
0x38ce2f  ldstr    aServicecallcou// "ServiceCallCount"
0x38ce34  ldc.i4.0
0x38ce35  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce3f  ldloc.0
0x38ce40  ldstr    aCreatingsitema// "CreatingSiteMaster"
0x38ce45  ldc.i4.2
0x38ce46  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce4b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce50  ldloc.0
0x38ce51  ldstr    aCreatefromsite// "CreateFromSiteMaster"
0x38ce56  ldc.i4.2
0x38ce57  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce5c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce61  ldloc.0
0x38ce62  ldstr    aBatchtablecopy// "BatchTableCopy"
0x38ce67  ldc.i4.2
0x38ce68  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce72  ldloc.0
0x38ce73  ldstr    aSitecopytimems// "SiteCopyTimeMs"
0x38ce78  ldc.i4.0
0x38ce79  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce7e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce83  ldloc.0
0x38ce84  ldstr    aSitecopysqlque// "SiteCopySqlQueryCount"
0x38ce89  ldc.i4.0
0x38ce8a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ce8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ce94  ldloc.0
0x38ce95  ldstr    aFeatureactivat_6// "FeatureActivationTimeMs"
0x38ce9a  ldc.i4.0
0x38ce9b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cea0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cea5  ldloc.0
0x38cea6  ldstr    aFeatureactivat_7// "FeatureActivationSqlQueryCount"
0x38ceab  ldc.i4.0
0x38ceac  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ceb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ceb6  ldloc.0
0x38ceb7  ldstr    aRowcopytimems// "RowCopyTimeMs"
0x38cebc  ldc.i4.0
0x38cebd  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cec2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cec7  ldloc.0
0x38cec8  ldstr    aSitedatabaseon// "SiteDatabaseOnSqlAzure"
0x38cecd  ldc.i4.2
0x38cece  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ced3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ced8  ldloc.0
0x38ced9  ldstr    aDatabasecheckm// "DatabaseCheckMillisec"
0x38cede  ldc.i4.0
0x38cedf  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cee4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cee9  ldloc.0
0x38ceea  ldstr    aSitemasterchec// "SiteMasterCheckMillisec"
0x38ceef  ldc.i4.0
0x38cef0  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cef5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cefa  ldloc.0
0x38cefb  ldstr    aConfigdbcreate// "ConfigDBCreateSiteMillisec"
0x38cf00  ldc.i4.0
0x38cf01  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf0b  ldloc.0
0x38cf0c  ldstr    aSprequestcreat// "SpRequestCreateSiteMillisec"
0x38cf11  ldc.i4.0
0x38cf12  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf17  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf1c  ldloc.0
0x38cf1d  ldstr    aQuotatemplatem// "QuotaTemplateMillisec"
0x38cf22  ldc.i4.0
0x38cf23  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf28  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf2d  ldloc.0
0x38cf2e  ldstr    aNonsitemasterb// "NonSiteMasterBasedCreationMillisec"
0x38cf33  ldc.i4.0
0x38cf34  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf39  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf3e  ldloc.0
0x38cf3f  ldstr    aEnsuresitemast// "EnsureSiteMasterMillisec"
0x38cf44  ldc.i4.0
0x38cf45  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf4a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf4f  ldloc.0
0x38cf50  ldstr    aUpdatesitesett// "UpdateSiteSettingsMillisec"
0x38cf55  ldc.i4.0
0x38cf56  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf5b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf60  ldloc.0
0x38cf61  ldstr    aUpdaterootwebp_2// "UpdateRootWebPropertiesMillisec"
0x38cf66  ldc.i4.0
0x38cf67  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf6c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf71  ldloc.0
0x38cf72  ldstr    aCopyfinalizati// "CopyFinalizationMillisec"
0x38cf77  ldc.i4.0
0x38cf78  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf7d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf82  ldloc.0
0x38cf83  ldstr    aUpdatesitesett_0// "UpdateSiteSettingsUserInfoMillisec"
0x38cf88  ldc.i4.0
0x38cf89  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf8e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cf93  ldloc.0
0x38cf94  ldstr    aUpdatesitesett_1// "UpdateSiteSettingsOwnerMillisec"
0x38cf99  ldc.i4.0
0x38cf9a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cf9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cfa4  ldloc.0
0x38cfa5  ldstr    aUpdatesitesett_2// "UpdateSiteSettingsSubscriptionMillisec"
0x38cfaa  ldc.i4.0
0x38cfab  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cfb0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cfb5  ldloc.0
0x38cfb6  ret
```
