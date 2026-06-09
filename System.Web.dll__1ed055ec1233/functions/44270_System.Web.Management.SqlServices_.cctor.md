# System.Web.Management.SqlServices::.cctor

- ea: `0x44270`
- end: `0x44464`
- name: `System.Web.Management.SqlServices::.cctor`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1959a0`

## string_xrefs

- `0x44270`: `InstallCommon.sql`
- `0x44293`: `InstallMembership.sql`
- `0x442a1`: `UninstallMembership.sql`
- `0x442d3`: `InstallProfile.sql`
- `0x442e1`: `UninstallProfile.sql`
- `0x44313`: `InstallRoles.sql`
- `0x44321`: `UninstallRoles.sql`
- `0x4435b`: `InstallPersonalization.sql`
- `0x44369`: `UninstallPersonalization.sql`
- `0x4437f`: `aspnet_Paths`
- `0x443ac`: `InstallWebEventSqlProvider.sql`
- `0x443ba`: `UninstallWebEventSqlProvider.sql`
- `0x443ef`: `UninstallCommon.sql`
- `0x4444f`: `InstallSqlState.sql`
- `0x44459`: `UninstallSqlState.sql`

## pseudocode

```c

```

## disassembly

```asm
0x44270  ldstr    aInstallcommonS// "InstallCommon.sql"
0x44275  stsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x4427a  ldc.i4.6
0x4427b  newarr   FeatureInfo
0x44280  dup
0x44281  ldc.i4.0
0x44282  ldc.i4.1
0x44283  ldc.i4.2
0x44284  newarr   [mscorlib]System.String
0x44289  dup
0x4428a  ldc.i4.0
0x4428b  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x44290  stelem.ref
0x44291  dup
0x44292  ldc.i4.1
0x44293  ldstr    aInstallmembers// "InstallMembership.sql"
0x44298  stelem.ref
0x44299  ldc.i4.1
0x4429a  newarr   [mscorlib]System.String
0x4429f  dup
0x442a0  ldc.i4.0
0x442a1  ldstr    aUninstallmembe// "UninstallMembership.sql"
0x442a6  stelem.ref
0x442a7  ldc.i4.1
0x442a8  newarr   [mscorlib]System.String
0x442ad  dup
0x442ae  ldc.i4.0
0x442af  ldstr    aAspnetMembersh// "aspnet_Membership"
0x442b4  stelem.ref
0x442b5  ldc.i4.1
0x442b6  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x442bb  stelem   FeatureInfo
0x442c0  dup
0x442c1  ldc.i4.1
0x442c2  ldc.i4.2
0x442c3  ldc.i4.2
0x442c4  newarr   [mscorlib]System.String
0x442c9  dup
0x442ca  ldc.i4.0
0x442cb  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x442d0  stelem.ref
0x442d1  dup
0x442d2  ldc.i4.1
0x442d3  ldstr    aInstallprofile// "InstallProfile.sql"
0x442d8  stelem.ref
0x442d9  ldc.i4.1
0x442da  newarr   [mscorlib]System.String
0x442df  dup
0x442e0  ldc.i4.0
0x442e1  ldstr    aUninstallprofi// "UninstallProfile.sql"
0x442e6  stelem.ref
0x442e7  ldc.i4.1
0x442e8  newarr   [mscorlib]System.String
0x442ed  dup
0x442ee  ldc.i4.0
0x442ef  ldstr    aAspnetProfile// "aspnet_Profile"
0x442f4  stelem.ref
0x442f5  ldc.i4.4
0x442f6  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x442fb  stelem   FeatureInfo
0x44300  dup
0x44301  ldc.i4.2
0x44302  ldc.i4.4
0x44303  ldc.i4.2
0x44304  newarr   [mscorlib]System.String
0x44309  dup
0x4430a  ldc.i4.0
0x4430b  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x44310  stelem.ref
0x44311  dup
0x44312  ldc.i4.1
0x44313  ldstr    aInstallrolesSq// "InstallRoles.sql"
0x44318  stelem.ref
0x44319  ldc.i4.1
0x4431a  newarr   [mscorlib]System.String
0x4431f  dup
0x44320  ldc.i4.0
0x44321  ldstr    aUninstallroles// "UninstallRoles.sql"
0x44326  stelem.ref
0x44327  ldc.i4.2
0x44328  newarr   [mscorlib]System.String
0x4432d  dup
0x4432e  ldc.i4.0
0x4432f  ldstr    aAspnetRoles// "aspnet_Roles"
0x44334  stelem.ref
0x44335  dup
0x44336  ldc.i4.1
0x44337  ldstr    aAspnetUsersinr// "aspnet_UsersInRoles"
0x4433c  stelem.ref
0x4433d  ldc.i4.2
0x4433e  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x44343  stelem   FeatureInfo
0x44348  dup
0x44349  ldc.i4.3
0x4434a  ldc.i4.8
0x4434b  ldc.i4.2
0x4434c  newarr   [mscorlib]System.String
0x44351  dup
0x44352  ldc.i4.0
0x44353  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x44358  stelem.ref
0x44359  dup
0x4435a  ldc.i4.1
0x4435b  ldstr    aInstallpersona// "InstallPersonalization.sql"
0x44360  stelem.ref
0x44361  ldc.i4.1
0x44362  newarr   [mscorlib]System.String
0x44367  dup
0x44368  ldc.i4.0
0x44369  ldstr    aUninstallperso// "UninstallPersonalization.sql"
0x4436e  stelem.ref
0x4436f  ldc.i4.3
0x44370  newarr   [mscorlib]System.String
0x44375  dup
0x44376  ldc.i4.0
0x44377  ldstr    aAspnetPersonal// "aspnet_PersonalizationPerUser"
0x4437c  stelem.ref
0x4437d  dup
0x4437e  ldc.i4.1
0x4437f  ldstr    aAspnetPaths// "aspnet_Paths"
0x44384  stelem.ref
0x44385  dup
0x44386  ldc.i4.2
0x44387  ldstr    aAspnetPersonal_0// "aspnet_PersonalizationAllUsers"
0x4438c  stelem.ref
0x4438d  ldc.i4.8
0x4438e  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x44393  stelem   FeatureInfo
0x44398  dup
0x44399  ldc.i4.4
0x4439a  ldc.i4.s 0x10
0x4439c  ldc.i4.2
0x4439d  newarr   [mscorlib]System.String
0x443a2  dup
0x443a3  ldc.i4.0
0x443a4  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x443a9  stelem.ref
0x443aa  dup
0x443ab  ldc.i4.1
0x443ac  ldstr    aInstallwebeven// "InstallWebEventSqlProvider.sql"
0x443b1  stelem.ref
0x443b2  ldc.i4.1
0x443b3  newarr   [mscorlib]System.String
0x443b8  dup
0x443b9  ldc.i4.0
0x443ba  ldstr    aUninstallwebev// "UninstallWebEventSqlProvider.sql"
0x443bf  stelem.ref
0x443c0  ldc.i4.1
0x443c1  newarr   [mscorlib]System.String
0x443c6  dup
0x443c7  ldc.i4.0
0x443c8  ldstr    aAspnetWebevent// "aspnet_WebEvent_Events"
0x443cd  stelem.ref
0x443ce  ldc.i4.s 0x10
0x443d0  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x443d5  stelem   FeatureInfo
0x443da  dup
0x443db  ldc.i4.5
0x443dc  ldc.i4   0x4000001F
0x443e1  ldc.i4.0
0x443e2  newarr   [mscorlib]System.String
0x443e7  ldc.i4.1
0x443e8  newarr   [mscorlib]System.String
0x443ed  dup
0x443ee  ldc.i4.0
0x443ef  ldstr    aUninstallcommo// "UninstallCommon.sql"
0x443f4  stelem.ref
0x443f5  ldc.i4.3
0x443f6  newarr   [mscorlib]System.String
0x443fb  dup
0x443fc  ldc.i4.0
0x443fd  ldstr    aAspnetApplicat// "aspnet_Applications"
0x44402  stelem.ref
0x44403  dup
0x44404  ldc.i4.1
0x44405  ldstr    aAspnetUsers// "aspnet_Users"
0x4440a  stelem.ref
0x4440b  dup
0x4440c  ldc.i4.2
0x4440d  ldstr    aAspnetSchemave// "aspnet_SchemaVersions"
0x44412  stelem.ref
0x44413  ldc.i4   0x7FFFFFFF
0x44418  newobj   instance void FeatureInfo::.ctor(valuetype System.Web.Management.SqlFeatures feature, string[] installFiles, string[] uninstallFiles, string[] tablesRemovedInUninstall, int32 dataCheckBitMask)
0x4441d  stelem   FeatureInfo
0x44422  stsfld   valuetype FeatureInfo[] System.Web.Management.SqlServices::s_featureInfos
0x44427  ldstr    aAspnetdb_1// "aspnetdb"
0x4442c  stsfld   string System.Web.Management.SqlServices::DEFAULT_DB
0x44431  ldstr    aAspstate_1// "ASPState"
0x44436  stsfld   string System.Web.Management.SqlServices::ASPSTATE_DB
0x4443b  ldstr    aSstypePersiste// "sstype_persisted"
0x44440  stsfld   string System.Web.Management.SqlServices::SSTYPE_PERSISTED
0x44445  ldstr    aSstypeCustom// "sstype_custom"
0x4444a  stsfld   string System.Web.Management.SqlServices::SSTYPE_CUSTOM
0x4444f  ldstr    aInstallsqlstat// "InstallSqlState.sql"
0x44454  stsfld   string System.Web.Management.SqlServices::SESSION_STATE_INSTALL_FILE
0x44459  ldstr    aUninstallsqlst// "UninstallSqlState.sql"
0x4445e  stsfld   string System.Web.Management.SqlServices::SESSION_STATE_UNINSTALL_FILE
0x44463  ret
```
