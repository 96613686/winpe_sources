# Microsoft.ReportingServices.Library.SystemPropertyNames::.cctor

- ea: `0x14f70`
- end: `0x152ea`
- name: `Microsoft.ReportingServices.Library.SystemPropertyNames::.cctor`
- size: `890`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14cb0`

## string_xrefs

- `0x15031`: `TokenUrl`
- `0x15183`: `TokenUrl`
- `0x15215`: `TokenUrl`
- `0x1508b`: `OAuthTokenUrl`
- `0x15266`: `OAuthTokenUrl`
- `0x14ff8`: `EnableIntegratedSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x14f70  ldc.i4.s 0xC
0x14f72  newarr   [mscorlib]System.String
0x14f77  dup
0x14f78  ldc.i4.0
0x14f79  ldstr    aSitename// "SiteName"
0x14f7e  stelem.ref
0x14f7f  dup
0x14f80  ldc.i4.1
0x14f81  ldstr    aEnablemyreport// "EnableMyReports"
0x14f86  stelem.ref
0x14f87  dup
0x14f88  ldc.i4.2
0x14f89  ldstr    aMyreportsrole// "MyReportsRole"
0x14f8e  stelem.ref
0x14f8f  dup
0x14f90  ldc.i4.3
0x14f91  ldstr    aUsesessioncook// "UseSessionCookies"
0x14f96  stelem.ref
0x14f97  dup
0x14f98  ldc.i4.4
0x14f99  ldstr    aSessiontimeout// "SessionTimeout"
0x14f9e  stelem.ref
0x14f9f  dup
0x14fa0  ldc.i4.5
0x14fa1  ldstr    aSystemreportti// "SystemReportTimeout"
0x14fa6  stelem.ref
0x14fa7  dup
0x14fa8  ldc.i4.6
0x14fa9  ldstr    aEnableexecutio// "EnableExecutionLogging"
0x14fae  stelem.ref
0x14faf  dup
0x14fb0  ldc.i4.7
0x14fb1  ldstr    aExecutionlogda// "ExecutionLogDaysKept"
0x14fb6  stelem.ref
0x14fb7  dup
0x14fb8  ldc.i4.8
0x14fb9  ldstr    aExecutionlogle// "ExecutionLogLevel"
0x14fbe  stelem.ref
0x14fbf  dup
0x14fc0  ldc.i4.s 9
0x14fc2  ldstr    aSystemsnapshot// "SystemSnapshotLimit"
0x14fc7  stelem.ref
0x14fc8  dup
0x14fc9  ldc.i4.s 0xA
0x14fcb  ldstr    aEnableclientpr// "EnableClientPrinting"
0x14fd0  stelem.ref
0x14fd1  dup
0x14fd2  ldc.i4.s 0xB
0x14fd4  ldstr    aRdlxreporttime// "RDLXReportTimeout"
0x14fd9  stelem.ref
0x14fda  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNonNullablePropertyNames
0x14fdf  ldc.i4.s 0x28
0x14fe1  newarr   [mscorlib]System.String
0x14fe6  dup
0x14fe7  ldc.i4.0
0x14fe8  ldstr    aSitename// "SiteName"
0x14fed  stelem.ref
0x14fee  dup
0x14fef  ldc.i4.1
0x14ff0  ldstr    aEnableclientpr// "EnableClientPrinting"
0x14ff5  stelem.ref
0x14ff6  dup
0x14ff7  ldc.i4.2
0x14ff8  ldstr    aEnableintegrat// "EnableIntegratedSecurity"
0x14ffd  stelem.ref
0x14ffe  dup
0x14fff  ldc.i4.3
0x15000  ldstr    aSharepointinte// "SharePointIntegrated"
0x15005  stelem.ref
0x15006  dup
0x15007  ldc.i4.4
0x15008  ldstr    aResourceurl// "ResourceUrl"
0x1500d  stelem.ref
0x1500e  dup
0x1500f  ldc.i4.5
0x15010  ldstr    aAuthorizationu// "AuthorizationUrl"
0x15015  stelem.ref
0x15016  dup
0x15017  ldc.i4.6
0x15018  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x1501d  stelem.ref
0x1501e  dup
0x1501f  ldc.i4.7
0x15020  ldstr    aRedirecturls// "RedirectUrls"
0x15025  stelem.ref
0x15026  dup
0x15027  ldc.i4.8
0x15028  ldstr    aLogouturl// "LogoutUrl"
0x1502d  stelem.ref
0x1502e  dup
0x1502f  ldc.i4.s 9
0x15031  ldstr    aTokenurl// "TokenUrl"
0x15036  stelem.ref
0x15037  dup
0x15038  ldc.i4.s 0xA
0x1503a  ldstr    aClientid// "ClientId"
0x1503f  stelem.ref
0x15040  dup
0x15041  ldc.i4.s 0xB
0x15043  ldstr    aClientsecret// "ClientSecret"
0x15048  stelem.ref
0x15049  dup
0x1504a  ldc.i4.s 0xC
0x1504c  ldstr    aAppobjectid// "AppObjectId"
0x15051  stelem.ref
0x15052  dup
0x15053  ldc.i4.s 0xD
0x15055  ldstr    aTenantname// "TenantName"
0x1505a  stelem.ref
0x1505b  dup
0x1505c  ldc.i4.s 0xE
0x1505e  ldstr    aTenantid// "TenantId"
0x15063  stelem.ref
0x15064  dup
0x15065  ldc.i4.s 0xF
0x15067  ldstr    aMaxfilesizemb// "MaxFileSizeMb"
0x1506c  stelem.ref
0x1506d  dup
0x1506e  ldc.i4.s 0x10
0x15070  ldstr    aOauthclientid// "OAuthClientId"
0x15075  stelem.ref
0x15076  dup
0x15077  ldc.i4.s 0x11
0x15079  ldstr    aOauthclientsec// "OAuthClientSecret"
0x1507e  stelem.ref
0x1507f  dup
0x15080  ldc.i4.s 0x12
0x15082  ldstr    aOauthtenant// "OAuthTenant"
0x15087  stelem.ref
0x15088  dup
0x15089  ldc.i4.s 0x13
0x1508b  ldstr    aOauthtokenurl// "OAuthTokenUrl"
0x15090  stelem.ref
0x15091  dup
0x15092  ldc.i4.s 0x14
0x15094  ldstr    aOauthauthoriza// "OAuthAuthorizationUrl"
0x15099  stelem.ref
0x1509a  dup
0x1509b  ldc.i4.s 0x15
0x1509d  ldstr    aOauthfederatio// "OAuthFederationMetadataUrl"
0x150a2  stelem.ref
0x150a3  dup
0x150a4  ldc.i4.s 0x16
0x150a6  ldstr    aOauthresourceu// "OAuthResourceUrl"
0x150ab  stelem.ref
0x150ac  dup
0x150ad  ldc.i4.s 0x17
0x150af  ldstr    aOauthnativecli// "OAuthNativeClientId"
0x150b4  stelem.ref
0x150b5  dup
0x150b6  ldc.i4.s 0x18
0x150b8  ldstr    aOauthgraphurl// "OAuthGraphUrl"
0x150bd  stelem.ref
0x150be  dup
0x150bf  ldc.i4.s 0x19
0x150c1  ldstr    aOauthsessionco// "OAuthSessionCookieName"
0x150c6  stelem.ref
0x150c7  dup
0x150c8  ldc.i4.s 0x1A
0x150ca  ldstr    aOauthlogouturl// "OAuthLogoutUrl"
0x150cf  stelem.ref
0x150d0  dup
0x150d1  ldc.i4.s 0x1B
0x150d3  ldstr    aRequireintune// "RequireIntune"
0x150d8  stelem.ref
0x150d9  dup
0x150da  ldc.i4.s 0x1C
0x150dc  ldstr    aSystemreportti// "SystemReportTimeout"
0x150e1  stelem.ref
0x150e2  dup
0x150e3  ldc.i4.s 0x1D
0x150e5  ldstr    aSystemsnapshot// "SystemSnapshotLimit"
0x150ea  stelem.ref
0x150eb  dup
0x150ec  ldc.i4.s 0x1E
0x150ee  ldstr    aOfficeonlinedi// "OfficeOnlineDiscoveryUrl"
0x150f3  stelem.ref
0x150f4  dup
0x150f5  ldc.i4.s 0x1F
0x150f7  ldstr    aExcelwopiclien// "ExcelWopiClientUrl"
0x150fc  stelem.ref
0x150fd  dup
0x150fe  ldc.i4.s 0x20
0x15100  ldstr    aShowdownloadme// "ShowDownloadMenu"
0x15105  stelem.ref
0x15106  dup
0x15107  ldc.i4.s 0x21
0x15109  ldstr    aCustomurllabel// "CustomUrlLabel"
0x1510e  stelem.ref
0x1510f  dup
0x15110  ldc.i4.s 0x22
0x15112  ldstr    aCustomurlvalue// "CustomUrlValue"
0x15117  stelem.ref
0x15118  dup
0x15119  ldc.i4.s 0x23
0x1511b  ldstr    aTileviewbydefa// "TileViewByDefault"
0x15120  stelem.ref
0x15121  dup
0x15122  ldc.i4.s 0x24
0x15124  ldstr    aEnablepowerbir// "EnablePowerBIReportMigrate"
0x15129  stelem.ref
0x1512a  dup
0x1512b  ldc.i4.s 0x25
0x1512d  ldstr    aPowerbimigrate// "PowerBIMigrateUrl"
0x15132  stelem.ref
0x15133  dup
0x15134  ldc.i4.s 0x26
0x15136  ldstr    aPowerbimigrate_0// "PowerBIMigrateCountLimit"
0x1513b  stelem.ref
0x1513c  dup
0x1513d  ldc.i4.s 0x27
0x1513f  ldstr    aEnablelisthist// "EnableListHistorySnapshotsSize"
0x15144  stelem.ref
0x15145  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNonPermissionedPropertyNames
0x1514a  ldc.i4.s 0xC
0x1514c  newarr   [mscorlib]System.String
0x15151  dup
0x15152  ldc.i4.0
0x15153  ldstr    aSharepointinte// "SharePointIntegrated"
0x15158  stelem.ref
0x15159  dup
0x1515a  ldc.i4.1
0x1515b  ldstr    aResourceurl// "ResourceUrl"
0x15160  stelem.ref
0x15161  dup
0x15162  ldc.i4.2
0x15163  ldstr    aAuthorizationu// "AuthorizationUrl"
0x15168  stelem.ref
0x15169  dup
0x1516a  ldc.i4.3
0x1516b  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x15170  stelem.ref
0x15171  dup
0x15172  ldc.i4.4
0x15173  ldstr    aRedirecturls// "RedirectUrls"
0x15178  stelem.ref
0x15179  dup
0x1517a  ldc.i4.5
0x1517b  ldstr    aLogouturl// "LogoutUrl"
0x15180  stelem.ref
0x15181  dup
0x15182  ldc.i4.6
0x15183  ldstr    aTokenurl// "TokenUrl"
0x15188  stelem.ref
0x15189  dup
0x1518a  ldc.i4.7
0x1518b  ldstr    aClientid// "ClientId"
0x15190  stelem.ref
0x15191  dup
0x15192  ldc.i4.8
0x15193  ldstr    aClientsecret// "ClientSecret"
0x15198  stelem.ref
0x15199  dup
0x1519a  ldc.i4.s 9
0x1519c  ldstr    aAppobjectid// "AppObjectId"
0x151a1  stelem.ref
0x151a2  dup
0x151a3  ldc.i4.s 0xA
0x151a5  ldstr    aTenantname// "TenantName"
0x151aa  stelem.ref
0x151ab  dup
0x151ac  ldc.i4.s 0xB
0x151ae  ldstr    aTenantid// "TenantId"
0x151b3  stelem.ref
0x151b4  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemReadOnlyPropertyNames
0x151b9  ldc.i4.1
0x151ba  newarr   [mscorlib]System.String
0x151bf  dup
0x151c0  ldc.i4.0
0x151c1  ldstr    aRdlxreporttime// "RDLXReportTimeout"
0x151c6  stelem.ref
0x151c7  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNativeModeNotSupportedPropertyNames
0x151cc  ldc.i4.s 0x17
0x151ce  newarr   [mscorlib]System.String
0x151d3  dup
0x151d4  ldc.i4.0
0x151d5  ldstr    aSitename// "SiteName"
0x151da  stelem.ref
0x151db  dup
0x151dc  ldc.i4.1
0x151dd  ldstr    aEnablemyreport// "EnableMyReports"
0x151e2  stelem.ref
0x151e3  dup
0x151e4  ldc.i4.2
0x151e5  ldstr    aMyreportsrole// "MyReportsRole"
0x151ea  stelem.ref
0x151eb  dup
0x151ec  ldc.i4.3
0x151ed  ldstr    aResourceurl// "ResourceUrl"
0x151f2  stelem.ref
0x151f3  dup
0x151f4  ldc.i4.4
0x151f5  ldstr    aAuthorizationu// "AuthorizationUrl"
0x151fa  stelem.ref
0x151fb  dup
0x151fc  ldc.i4.5
0x151fd  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x15202  stelem.ref
0x15203  dup
0x15204  ldc.i4.6
  ... truncated ...
```
