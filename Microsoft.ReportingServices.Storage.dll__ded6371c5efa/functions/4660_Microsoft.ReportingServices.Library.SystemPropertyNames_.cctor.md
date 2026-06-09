# Microsoft.ReportingServices.Library.SystemPropertyNames::.cctor

- ea: `0x4660`
- end: `0x49da`
- name: `Microsoft.ReportingServices.Library.SystemPropertyNames::.cctor`
- size: `890`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x43a0`

## string_xrefs

- `0x46e8`: `EnableIntegratedSecurity`
- `0x4721`: `TokenUrl`
- `0x4873`: `TokenUrl`
- `0x4905`: `TokenUrl`
- `0x477b`: `OAuthTokenUrl`
- `0x4956`: `OAuthTokenUrl`

## pseudocode

```c

```

## disassembly

```asm
0x4660  ldc.i4.s 0xC
0x4662  newarr   [mscorlib]System.String
0x4667  dup
0x4668  ldc.i4.0
0x4669  ldstr    aSitename// "SiteName"
0x466e  stelem.ref
0x466f  dup
0x4670  ldc.i4.1
0x4671  ldstr    aEnablemyreport// "EnableMyReports"
0x4676  stelem.ref
0x4677  dup
0x4678  ldc.i4.2
0x4679  ldstr    aMyreportsrole// "MyReportsRole"
0x467e  stelem.ref
0x467f  dup
0x4680  ldc.i4.3
0x4681  ldstr    aUsesessioncook// "UseSessionCookies"
0x4686  stelem.ref
0x4687  dup
0x4688  ldc.i4.4
0x4689  ldstr    aSessiontimeout// "SessionTimeout"
0x468e  stelem.ref
0x468f  dup
0x4690  ldc.i4.5
0x4691  ldstr    aSystemreportti// "SystemReportTimeout"
0x4696  stelem.ref
0x4697  dup
0x4698  ldc.i4.6
0x4699  ldstr    aEnableexecutio// "EnableExecutionLogging"
0x469e  stelem.ref
0x469f  dup
0x46a0  ldc.i4.7
0x46a1  ldstr    aExecutionlogda// "ExecutionLogDaysKept"
0x46a6  stelem.ref
0x46a7  dup
0x46a8  ldc.i4.8
0x46a9  ldstr    aExecutionlogle// "ExecutionLogLevel"
0x46ae  stelem.ref
0x46af  dup
0x46b0  ldc.i4.s 9
0x46b2  ldstr    aSystemsnapshot// "SystemSnapshotLimit"
0x46b7  stelem.ref
0x46b8  dup
0x46b9  ldc.i4.s 0xA
0x46bb  ldstr    aEnableclientpr// "EnableClientPrinting"
0x46c0  stelem.ref
0x46c1  dup
0x46c2  ldc.i4.s 0xB
0x46c4  ldstr    aRdlxreporttime// "RDLXReportTimeout"
0x46c9  stelem.ref
0x46ca  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNonNullablePropertyNames
0x46cf  ldc.i4.s 0x28
0x46d1  newarr   [mscorlib]System.String
0x46d6  dup
0x46d7  ldc.i4.0
0x46d8  ldstr    aSitename// "SiteName"
0x46dd  stelem.ref
0x46de  dup
0x46df  ldc.i4.1
0x46e0  ldstr    aEnableclientpr// "EnableClientPrinting"
0x46e5  stelem.ref
0x46e6  dup
0x46e7  ldc.i4.2
0x46e8  ldstr    aEnableintegrat// "EnableIntegratedSecurity"
0x46ed  stelem.ref
0x46ee  dup
0x46ef  ldc.i4.3
0x46f0  ldstr    aSharepointinte// "SharePointIntegrated"
0x46f5  stelem.ref
0x46f6  dup
0x46f7  ldc.i4.4
0x46f8  ldstr    aResourceurl// "ResourceUrl"
0x46fd  stelem.ref
0x46fe  dup
0x46ff  ldc.i4.5
0x4700  ldstr    aAuthorizationu// "AuthorizationUrl"
0x4705  stelem.ref
0x4706  dup
0x4707  ldc.i4.6
0x4708  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x470d  stelem.ref
0x470e  dup
0x470f  ldc.i4.7
0x4710  ldstr    aRedirecturls// "RedirectUrls"
0x4715  stelem.ref
0x4716  dup
0x4717  ldc.i4.8
0x4718  ldstr    aLogouturl// "LogoutUrl"
0x471d  stelem.ref
0x471e  dup
0x471f  ldc.i4.s 9
0x4721  ldstr    aTokenurl// "TokenUrl"
0x4726  stelem.ref
0x4727  dup
0x4728  ldc.i4.s 0xA
0x472a  ldstr    aClientid// "ClientId"
0x472f  stelem.ref
0x4730  dup
0x4731  ldc.i4.s 0xB
0x4733  ldstr    aClientsecret// "ClientSecret"
0x4738  stelem.ref
0x4739  dup
0x473a  ldc.i4.s 0xC
0x473c  ldstr    aAppobjectid// "AppObjectId"
0x4741  stelem.ref
0x4742  dup
0x4743  ldc.i4.s 0xD
0x4745  ldstr    aTenantname// "TenantName"
0x474a  stelem.ref
0x474b  dup
0x474c  ldc.i4.s 0xE
0x474e  ldstr    aTenantid// "TenantId"
0x4753  stelem.ref
0x4754  dup
0x4755  ldc.i4.s 0xF
0x4757  ldstr    aMaxfilesizemb// "MaxFileSizeMb"
0x475c  stelem.ref
0x475d  dup
0x475e  ldc.i4.s 0x10
0x4760  ldstr    aOauthclientid// "OAuthClientId"
0x4765  stelem.ref
0x4766  dup
0x4767  ldc.i4.s 0x11
0x4769  ldstr    aOauthclientsec// "OAuthClientSecret"
0x476e  stelem.ref
0x476f  dup
0x4770  ldc.i4.s 0x12
0x4772  ldstr    aOauthtenant// "OAuthTenant"
0x4777  stelem.ref
0x4778  dup
0x4779  ldc.i4.s 0x13
0x477b  ldstr    aOauthtokenurl// "OAuthTokenUrl"
0x4780  stelem.ref
0x4781  dup
0x4782  ldc.i4.s 0x14
0x4784  ldstr    aOauthauthoriza// "OAuthAuthorizationUrl"
0x4789  stelem.ref
0x478a  dup
0x478b  ldc.i4.s 0x15
0x478d  ldstr    aOauthfederatio// "OAuthFederationMetadataUrl"
0x4792  stelem.ref
0x4793  dup
0x4794  ldc.i4.s 0x16
0x4796  ldstr    aOauthresourceu// "OAuthResourceUrl"
0x479b  stelem.ref
0x479c  dup
0x479d  ldc.i4.s 0x17
0x479f  ldstr    aOauthnativecli// "OAuthNativeClientId"
0x47a4  stelem.ref
0x47a5  dup
0x47a6  ldc.i4.s 0x18
0x47a8  ldstr    aOauthgraphurl// "OAuthGraphUrl"
0x47ad  stelem.ref
0x47ae  dup
0x47af  ldc.i4.s 0x19
0x47b1  ldstr    aOauthsessionco// "OAuthSessionCookieName"
0x47b6  stelem.ref
0x47b7  dup
0x47b8  ldc.i4.s 0x1A
0x47ba  ldstr    aOauthlogouturl// "OAuthLogoutUrl"
0x47bf  stelem.ref
0x47c0  dup
0x47c1  ldc.i4.s 0x1B
0x47c3  ldstr    aRequireintune// "RequireIntune"
0x47c8  stelem.ref
0x47c9  dup
0x47ca  ldc.i4.s 0x1C
0x47cc  ldstr    aSystemreportti// "SystemReportTimeout"
0x47d1  stelem.ref
0x47d2  dup
0x47d3  ldc.i4.s 0x1D
0x47d5  ldstr    aSystemsnapshot// "SystemSnapshotLimit"
0x47da  stelem.ref
0x47db  dup
0x47dc  ldc.i4.s 0x1E
0x47de  ldstr    aOfficeonlinedi// "OfficeOnlineDiscoveryUrl"
0x47e3  stelem.ref
0x47e4  dup
0x47e5  ldc.i4.s 0x1F
0x47e7  ldstr    aExcelwopiclien// "ExcelWopiClientUrl"
0x47ec  stelem.ref
0x47ed  dup
0x47ee  ldc.i4.s 0x20
0x47f0  ldstr    aShowdownloadme// "ShowDownloadMenu"
0x47f5  stelem.ref
0x47f6  dup
0x47f7  ldc.i4.s 0x21
0x47f9  ldstr    aCustomurllabel// "CustomUrlLabel"
0x47fe  stelem.ref
0x47ff  dup
0x4800  ldc.i4.s 0x22
0x4802  ldstr    aCustomurlvalue// "CustomUrlValue"
0x4807  stelem.ref
0x4808  dup
0x4809  ldc.i4.s 0x23
0x480b  ldstr    aTileviewbydefa// "TileViewByDefault"
0x4810  stelem.ref
0x4811  dup
0x4812  ldc.i4.s 0x24
0x4814  ldstr    aEnablepowerbir// "EnablePowerBIReportMigrate"
0x4819  stelem.ref
0x481a  dup
0x481b  ldc.i4.s 0x25
0x481d  ldstr    aPowerbimigrate// "PowerBIMigrateUrl"
0x4822  stelem.ref
0x4823  dup
0x4824  ldc.i4.s 0x26
0x4826  ldstr    aPowerbimigrate_0// "PowerBIMigrateCountLimit"
0x482b  stelem.ref
0x482c  dup
0x482d  ldc.i4.s 0x27
0x482f  ldstr    aEnablelisthist// "EnableListHistorySnapshotsSize"
0x4834  stelem.ref
0x4835  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNonPermissionedPropertyNames
0x483a  ldc.i4.s 0xC
0x483c  newarr   [mscorlib]System.String
0x4841  dup
0x4842  ldc.i4.0
0x4843  ldstr    aSharepointinte// "SharePointIntegrated"
0x4848  stelem.ref
0x4849  dup
0x484a  ldc.i4.1
0x484b  ldstr    aResourceurl// "ResourceUrl"
0x4850  stelem.ref
0x4851  dup
0x4852  ldc.i4.2
0x4853  ldstr    aAuthorizationu// "AuthorizationUrl"
0x4858  stelem.ref
0x4859  dup
0x485a  ldc.i4.3
0x485b  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x4860  stelem.ref
0x4861  dup
0x4862  ldc.i4.4
0x4863  ldstr    aRedirecturls// "RedirectUrls"
0x4868  stelem.ref
0x4869  dup
0x486a  ldc.i4.5
0x486b  ldstr    aLogouturl// "LogoutUrl"
0x4870  stelem.ref
0x4871  dup
0x4872  ldc.i4.6
0x4873  ldstr    aTokenurl// "TokenUrl"
0x4878  stelem.ref
0x4879  dup
0x487a  ldc.i4.7
0x487b  ldstr    aClientid// "ClientId"
0x4880  stelem.ref
0x4881  dup
0x4882  ldc.i4.8
0x4883  ldstr    aClientsecret// "ClientSecret"
0x4888  stelem.ref
0x4889  dup
0x488a  ldc.i4.s 9
0x488c  ldstr    aAppobjectid// "AppObjectId"
0x4891  stelem.ref
0x4892  dup
0x4893  ldc.i4.s 0xA
0x4895  ldstr    aTenantname// "TenantName"
0x489a  stelem.ref
0x489b  dup
0x489c  ldc.i4.s 0xB
0x489e  ldstr    aTenantid// "TenantId"
0x48a3  stelem.ref
0x48a4  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemReadOnlyPropertyNames
0x48a9  ldc.i4.1
0x48aa  newarr   [mscorlib]System.String
0x48af  dup
0x48b0  ldc.i4.0
0x48b1  ldstr    aRdlxreporttime// "RDLXReportTimeout"
0x48b6  stelem.ref
0x48b7  stsfld   string[] Microsoft.ReportingServices.Library.SystemPropertyNames::SystemNativeModeNotSupportedPropertyNames
0x48bc  ldc.i4.s 0x17
0x48be  newarr   [mscorlib]System.String
0x48c3  dup
0x48c4  ldc.i4.0
0x48c5  ldstr    aSitename// "SiteName"
0x48ca  stelem.ref
0x48cb  dup
0x48cc  ldc.i4.1
0x48cd  ldstr    aEnablemyreport// "EnableMyReports"
0x48d2  stelem.ref
0x48d3  dup
0x48d4  ldc.i4.2
0x48d5  ldstr    aMyreportsrole// "MyReportsRole"
0x48da  stelem.ref
0x48db  dup
0x48dc  ldc.i4.3
0x48dd  ldstr    aResourceurl// "ResourceUrl"
0x48e2  stelem.ref
0x48e3  dup
0x48e4  ldc.i4.4
0x48e5  ldstr    aAuthorizationu// "AuthorizationUrl"
0x48ea  stelem.ref
0x48eb  dup
0x48ec  ldc.i4.5
0x48ed  ldstr    aPowerbiendpoin// "PowerBIEndpoint"
0x48f2  stelem.ref
0x48f3  dup
0x48f4  ldc.i4.6
  ... truncated ...
```
