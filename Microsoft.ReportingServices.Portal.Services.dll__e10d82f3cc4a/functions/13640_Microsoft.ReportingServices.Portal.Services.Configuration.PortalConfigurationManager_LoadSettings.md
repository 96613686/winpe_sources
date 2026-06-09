# Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::LoadSettings

- ea: `0x13640`
- end: `0x138d4`
- name: `Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::LoadSettings`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x135e0`

## callees

- `0x12830`
- `0x12f60`
- `0x12f80`
- `0x13250`
- `0x13260`
- `0x13280`
- `0x132a0`
- `0x132c0`
- `0x132e0`
- `0x132f0`
- `0x13300`
- `0x13320`
- `0x13340`
- `0x13360`
- `0x13380`
- `0x133a0`
- `0x133c0`
- `0x133e0`
- `0x13400`
- `0x13420`
- `0x13440`
- `0x13460`
- `0x13480`
- `0x134a0`
- `0x134c0`
- `0x134e0`
- `0x13500`
- `0x13510`
- `0x13640`
- `0x138e0`
- `0x13920`
- `0x13980`
- `0x139b0`

## string_xrefs

- `0x1365d`: `Unable to load RS Configuration, error: `
- `0x136c8`: `Hosting-url-ReportServerWebService`
- `0x13713`: `Hosting-url-PowerBIService`

## pseudocode

```c

```

## disassembly

```asm
0x13640  ldnull
0x13641  stloc.0
0x13642  ldarg.0
0x13643  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::_configProvider
0x13648  callvirt instance object [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IRsConfigProvider::Load()
0x1364d  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration
0x13652  stloc.0
0x13653  leave.s  loc_1366F
0x13655  stloc.2
0x13656  ldarg.0
0x13657  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::_logger
0x1365c  ldc.i4.1
0x1365d  ldstr    aUnableToLoadRs// "Unable to load RS Configuration, error:"...
0x13662  ldloc.2
0x13663  call     string [mscorlib]System.String::Concat(object, object)
0x13668  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1366d  leave.s  loc_1366F
0x1366f  newobj   instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::.ctor()
0x13674  dup
0x13675  ldloc.0
0x13676  call     bool Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::IsRSWebAppConfigured(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration config)
0x1367b  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_AppConfigured(bool value)
0x13680  stloc.1
0x13681  ldloc.1
0x13682  callvirt instance bool Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::get_AppConfigured()
0x13687  brfalse  loc_138D2
0x1368c  ldloc.1
0x1368d  ldc.i4.3
0x1368e  ldloc.0
0x1368f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_UrlConfiguration()
0x13694  call     string Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetVirtualRoot(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication app, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> urlConfig)
0x13699  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_ReportServerWebAppVirtualDirectory(string value)
0x1369e  ldloc.1
0x1369f  ldc.i4.3
0x136a0  ldloc.0
0x136a1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_UrlConfiguration()
0x136a6  call     string[] Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetUrls(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication app, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> urlConfig)
0x136ab  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_RegisteredWebAppUrls(string[] value)
0x136b0  ldloc.1
0x136b1  ldc.i4.1
0x136b2  ldloc.0
0x136b3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_UrlConfiguration()
0x136b8  call     string[] Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::GetUrls(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication app, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.UrlConfiguration> urlConfig)
0x136bd  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_RegisteredReportServerUrls(string[] value)
0x136c2  ldloc.1
0x136c3  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x136c8  ldstr    aHostingUrlRepo// "Hosting-url-ReportServerWebService"
0x136cd  ldsfld   string [mscorlib]System.String::Empty
0x136d2  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x136d7  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_ReportServerUrl(string value)
0x136dc  ldloc.1
0x136dd  callvirt instance string Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::get_ReportServerUrl()
0x136e2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x136e7  brtrue.s loc_136F6
0x136e9  ldloc.1
0x136ea  callvirt instance string Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::get_ReportServerUrl()
0x136ef  newobj   instance void [System]System.Uri::.ctor(string)
0x136f4  br.s     loc_13700
0x136f6  ldstr    aHttpLocalhost// "http://localhost"
0x136fb  newobj   instance void [System]System.Uri::.ctor(string)
0x13700  stloc.3
0x13701  ldloc.1
0x13702  ldloc.3
0x13703  callvirt instance string [System]System.Uri::get_Host()
0x13708  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_ReportServerHostName(string value)
0x1370d  ldloc.1
0x1370e  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x13713  ldstr    aHostingUrlPowe// "Hosting-url-PowerBIService"
0x13718  ldsfld   string [mscorlib]System.String::Empty
0x1371d  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, string)
0x13722  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_PowerBIUrl(string value)
0x13727  ldloc.1
0x13728  ldloc.0
0x13729  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_ReportServerVirtualDirectory()
0x1372e  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_ReportServerVirtualDirectory(string value)
0x13733  ldloc.1
0x13734  ldloc.0
0x13735  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthenticationTypes()
0x1373a  call     valuetype [System]System.Net.AuthenticationSchemes Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfigurationManager::Convert(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes authenticationTypes)
0x1373f  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_AuthenticationSchemes(valuetype [System]System.Net.AuthenticationSchemes value)
0x13744  ldloc.1
0x13745  ldloc.0
0x13746  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthenticationTypes()
0x1374b  conv.u1
0x1374c  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_AuthenticationTypes(int32 value)
0x13751  ldloc.1
0x13752  ldloc.0
0x13753  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthPersistence()
0x13758  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_AuthPersistence(bool value)
0x1375d  ldloc.1
0x1375e  ldloc.0
0x1375f  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_MaxActiveReqForOneUser()
0x13764  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_MaxActiveReqForOneUser(int32 value)
0x13769  ldloc.1
0x1376a  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x1376f  brtrue.s loc_13774
0x13771  ldnull
0x13772  br.s     loc_1377E
0x13774  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13779  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x1377e  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_InstanceID(string value)
0x13783  ldloc.1
0x13784  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13789  brtrue.s loc_13792
0x1378b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13790  br.s     loc_1379C
0x13792  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13797  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstallationID()
0x1379c  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_InstallationId(valuetype [mscorlib]System.Guid value)
0x137a1  ldloc.1
0x137a2  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FileSizeRestrictions::.ctor()
0x137a7  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_FileSizeRestrictions(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions value)
0x137ac  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137b1  brfalse.s loc_13801
0x137b3  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137b8  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration/CatalogConnectionAuth [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ConnectionAuth()
0x137bd  brtrue.s loc_13801
0x137bf  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137c4  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration/CatalogConnectionType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_ConnectionType()
0x137c9  ldc.i4.1
0x137ca  bne.un.s loc_13801
0x137cc  ldloc.1
0x137cd  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137d2  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_BaseConnectionString()
0x137d7  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137dc  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogUser()
0x137e1  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137e6  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogDomain()
0x137eb  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x137f0  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_CatalogCred()
0x137f5  newobj   instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::.ctor(string connectionString, string windowsUser, string windowsDomain, string windowsPassword)
0x137fa  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_CatalogConfiguration(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogConfiguration value)
0x137ff  br.s     loc_1382C
0x13801  ldnull
0x13802  stloc.s  4
0x13804  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13809  brtrue.s loc_1380E
0x1380b  ldnull
0x1380c  br.s     loc_13818
0x1380e  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x13813  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_BaseConnectionString()
0x13818  stloc.s  4
0x1381a  leave.s  loc_1381F
0x1381c  pop
0x1381d  leave.s  loc_1381F
0x1381f  ldloc.1
0x13820  ldloc.s  4
0x13822  newobj   instance void Microsoft.ReportingServices.Portal.Services.Configuration.CatalogConfiguration::.ctor(string connectionString)
0x13827  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_CatalogConfiguration(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogConfiguration value)
0x1382c  ldloc.0
0x1382d  callvirt instance class [System]System.Collections.Specialized.StringCollection [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_PassthroughCookies()
0x13832  brfalse.s loc_1384A
0x13834  ldloc.1
0x13835  ldloc.0
0x13836  callvirt instance class [System]System.Collections.Specialized.StringCollection [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_PassthroughCookies()
0x1383b  call     T0x2B00004E
0x13840  call     T0x2B00008F
0x13845  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_PassthroughCookies(string[] value)
0x1384a  ldloc.0
0x1384b  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthenticationTypes()
0x13850  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes
0x13855  ldc.i4.8
0x13856  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes
0x1385b  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x13860  brfalse.s loc_1388B
0x13862  ldloc.1
0x13863  ldloc.0
0x13864  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.LogonMethod [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_LogonMethod()
0x13869  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.LogonType Microsoft.ReportingServices.Portal.Services.Extensions.LogonMethodExtensions::ToLogonType(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.LogonMethod logonMethod)
0x1386e  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_BasicAuthenticationLogonType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.LogonType value)
0x13873  ldloc.1
0x13874  ldloc.0
0x13875  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthRealm()
0x1387a  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_BasicAuthenticationRealm(string value)
0x1387f  ldloc.1
0x13880  ldloc.0
0x13881  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthDomain()
0x13886  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_BasicAuthenticationDomain(string value)
0x1388b  ldloc.0
0x1388c  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_AuthenticationTypes()
0x13891  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes
0x13896  ldc.i4.s 0x40
0x13898  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes
0x1389d  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x138a2  brfalse.s loc_138B0
0x138a4  ldloc.1
0x138a5  ldloc.0
0x138a6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IRSPortalConfiguration::get_OAuthConfiguration()
0x138ab  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_OAuthConfiguration(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IOAuthConfiguration value)
0x138b0  ldloc.1
0x138b1  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x138b6  ldc.i4.s 0x12
0x138b8  stloc.s  5
0x138ba  ldloca.s 5
0x138bc  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches
0x138c2  callvirt instance string [mscorlib]System.Object::ToString()
0x138c7  ldc.i4.0
0x138c8  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault(string, bool)
0x138cd  callvirt instance void Microsoft.ReportingServices.Portal.Services.Configuration.PortalConfiguration::set_LogClientIPAddress(bool value)
0x138d2  ldloc.1
0x138d3  ret
```
