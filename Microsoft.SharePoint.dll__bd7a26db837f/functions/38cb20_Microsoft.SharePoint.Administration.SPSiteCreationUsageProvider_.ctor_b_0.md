# Microsoft.SharePoint.Administration.SPSiteCreationUsageProvider::<.ctor>b__0

- ea: `0x38cb20`
- end: `0x38cd67`
- name: `Microsoft.SharePoint.Administration.SPSiteCreationUsageProvider::<.ctor>b__0`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x378200`
- `0x378210`

## string_xrefs

- `0x38cbdf`: `ServiceCallCount`
- `0x38cbce`: `ServiceCallDuration`
- `0x38cb3a`: `RootWebTemplate`
- `0x38cc01`: `CreateFromSiteMaster`
- `0x38cc12`: `BatchTableCopy`
- `0x38cc23`: `SiteCopyTimeMs`
- `0x38cc34`: `SiteCopySqlQueryCount`
- `0x38cc67`: `RowCopyTimeMs`
- `0x38ccab`: `ConfigDBCreateSiteMillisec`
- `0x38ccbc`: `SpRequestCreateSiteMillisec`
- `0x38cccd`: `QuotaTemplateMillisec`
- `0x38cd00`: `UpdateSiteSettingsMillisec`
- `0x38cd11`: `UpdateRootWebPropertiesMillisec`
- `0x38cd22`: `CopyFinalizationMillisec`
- `0x38cd33`: `UpdateSiteSettingsUserInfoMillisec`
- `0x38cd44`: `UpdateSiteSettingsOwnerMillisec`
- `0x38cd55`: `UpdateSiteSettingsSubscriptionMillisec`

## pseudocode

```c

```

## disassembly

```asm
0x38cb20  ldc.i4.1
0x38cb21  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::.ctor(int32)
0x38cb26  stloc.0
0x38cb27  ldloc.0
0x38cb28  ldstr    aSiteid_0// "SiteId"
0x38cb2d  ldc.i4.s 0xE
0x38cb2f  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cb34  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb39  ldloc.0
0x38cb3a  ldstr    aRootwebtemplat// "RootWebTemplate"
0x38cb3f  ldc.i4.s 0xC
0x38cb41  ldc.i4   0x80
0x38cb46  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38cb4b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb50  ldloc.0
0x38cb51  ldstr    aCreationtimems// "CreationTimeMs"
0x38cb56  ldc.i4.0
0x38cb57  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cb5c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb61  ldloc.0
0x38cb62  ldstr    aSqlquerycount// "SqlQueryCount"
0x38cb67  ldc.i4.0
0x38cb68  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cb6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb72  ldloc.0
0x38cb73  ldstr    aSqlquerytime// "SqlQueryTime"
0x38cb78  ldc.i4.0
0x38cb79  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cb7e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb83  ldloc.0
0x38cb84  ldstr    aSqlconnectiont// "SqlConnectionTime"
0x38cb89  ldc.i4.0
0x38cb8a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cb8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cb94  ldloc.0
0x38cb95  ldstr    aSlowestqueryda// "SlowestQueryDatabase"
0x38cb9a  ldc.i4.s 0xC
0x38cb9c  ldc.i4   0x80
0x38cba1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type, int32 size)
0x38cba6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cbab  ldloc.0
0x38cbac  ldstr    aCpuduration// "CpuDuration"
0x38cbb1  ldc.i4.0
0x38cbb2  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cbb7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cbbc  ldloc.0
0x38cbbd  ldstr    aCpucycles// "CpuCycles"
0x38cbc2  ldc.i4.0
0x38cbc3  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cbc8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cbcd  ldloc.0
0x38cbce  ldstr    aServicecalldur_0// "ServiceCallDuration"
0x38cbd3  ldc.i4.0
0x38cbd4  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cbd9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cbde  ldloc.0
0x38cbdf  ldstr    aServicecallcou// "ServiceCallCount"
0x38cbe4  ldc.i4.0
0x38cbe5  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cbea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cbef  ldloc.0
0x38cbf0  ldstr    aCreatingsitema// "CreatingSiteMaster"
0x38cbf5  ldc.i4.2
0x38cbf6  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cbfb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc00  ldloc.0
0x38cc01  ldstr    aCreatefromsite// "CreateFromSiteMaster"
0x38cc06  ldc.i4.2
0x38cc07  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc11  ldloc.0
0x38cc12  ldstr    aBatchtablecopy// "BatchTableCopy"
0x38cc17  ldc.i4.2
0x38cc18  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc1d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc22  ldloc.0
0x38cc23  ldstr    aSitecopytimems// "SiteCopyTimeMs"
0x38cc28  ldc.i4.0
0x38cc29  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc33  ldloc.0
0x38cc34  ldstr    aSitecopysqlque// "SiteCopySqlQueryCount"
0x38cc39  ldc.i4.0
0x38cc3a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc3f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc44  ldloc.0
0x38cc45  ldstr    aFeatureactivat_6// "FeatureActivationTimeMs"
0x38cc4a  ldc.i4.0
0x38cc4b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc55  ldloc.0
0x38cc56  ldstr    aFeatureactivat_7// "FeatureActivationSqlQueryCount"
0x38cc5b  ldc.i4.0
0x38cc5c  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc66  ldloc.0
0x38cc67  ldstr    aRowcopytimems// "RowCopyTimeMs"
0x38cc6c  ldc.i4.0
0x38cc6d  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc77  ldloc.0
0x38cc78  ldstr    aSitedatabaseon// "SiteDatabaseOnSqlAzure"
0x38cc7d  ldc.i4.2
0x38cc7e  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc88  ldloc.0
0x38cc89  ldstr    aDatabasecheckm// "DatabaseCheckMillisec"
0x38cc8e  ldc.i4.0
0x38cc8f  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cc94  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cc99  ldloc.0
0x38cc9a  ldstr    aSitemasterchec// "SiteMasterCheckMillisec"
0x38cc9f  ldc.i4.0
0x38cca0  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cca5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ccaa  ldloc.0
0x38ccab  ldstr    aConfigdbcreate// "ConfigDBCreateSiteMillisec"
0x38ccb0  ldc.i4.0
0x38ccb1  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ccb6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ccbb  ldloc.0
0x38ccbc  ldstr    aSprequestcreat// "SpRequestCreateSiteMillisec"
0x38ccc1  ldc.i4.0
0x38ccc2  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ccc7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cccc  ldloc.0
0x38cccd  ldstr    aQuotatemplatem// "QuotaTemplateMillisec"
0x38ccd2  ldc.i4.0
0x38ccd3  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ccd8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ccdd  ldloc.0
0x38ccde  ldstr    aNonsitemasterb// "NonSiteMasterBasedCreationMillisec"
0x38cce3  ldc.i4.0
0x38cce4  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cce9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ccee  ldloc.0
0x38ccef  ldstr    aEnsuresitemast// "EnsureSiteMasterMillisec"
0x38ccf4  ldc.i4.0
0x38ccf5  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38ccfa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38ccff  ldloc.0
0x38cd00  ldstr    aUpdatesitesett// "UpdateSiteSettingsMillisec"
0x38cd05  ldc.i4.0
0x38cd06  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd10  ldloc.0
0x38cd11  ldstr    aUpdaterootwebp_2// "UpdateRootWebPropertiesMillisec"
0x38cd16  ldc.i4.0
0x38cd17  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd21  ldloc.0
0x38cd22  ldstr    aCopyfinalizati// "CopyFinalizationMillisec"
0x38cd27  ldc.i4.0
0x38cd28  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd2d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd32  ldloc.0
0x38cd33  ldstr    aUpdatesitesett_0// "UpdateSiteSettingsUserInfoMillisec"
0x38cd38  ldc.i4.0
0x38cd39  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd43  ldloc.0
0x38cd44  ldstr    aUpdatesitesett_1// "UpdateSiteSettingsOwnerMillisec"
0x38cd49  ldc.i4.0
0x38cd4a  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd54  ldloc.0
0x38cd55  ldstr    aUpdatesitesett_2// "UpdateSiteSettingsSubscriptionMillisec"
0x38cd5a  ldc.i4.0
0x38cd5b  newobj   instance void Microsoft.SharePoint.Administration.SPColumnDefinition::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType type)
0x38cd60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPColumnDefinition>::Add(var<u1>)
0x38cd65  ldloc.0
0x38cd66  ret
```
