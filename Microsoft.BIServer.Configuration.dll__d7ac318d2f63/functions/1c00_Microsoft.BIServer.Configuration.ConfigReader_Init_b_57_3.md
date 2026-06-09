# Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_3

- ea: `0x1c00`
- end: `0x1d65`
- name: `Microsoft.BIServer.Configuration.ConfigReader::<Init>b__57_3`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `47`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8c0`
- `0x8e0`
- `0x900`
- `0x920`
- `0x940`
- `0x960`
- `0x980`
- `0x9a0`
- `0x9c0`
- `0x9e0`
- `0xa00`
- `0xa20`
- `0xa40`
- `0xa60`
- `0xa80`
- `0xaa0`
- `0xac0`
- `0xae0`
- `0xb00`
- `0xb20`
- `0xb40`
- `0xb60`
- `0xb80`
- `0xba0`
- `0xbb0`
- `0x1030`
- `0x1250`
- `0x12b0`
- `0x1360`
- `0x1430`
- `0x1500`
- `0x17c0`
- `0x1870`
- `0x1980`
- `0x19e0`
- `0x1a20`
- `0x1a60`
- `0x1aa0`
- `0x1ae0`
- `0x1b40`
- `0x1b60`
- `0x1b80`
- `0x3c60`
- `0x3c80`
- `0x3ca0`
- `0x3cd0`
- `0x3d00`

## string_xrefs

- `0x1ce6`: `ReportServerWebService`
- `0x1d08`: `ReportServerWebService`

## pseudocode

```c

```

## disassembly

```asm
0x1c00  newobj   instance void Microsoft.BIServer.Configuration.ServerConfiguration::.ctor()
0x1c05  dup
0x1c06  ldarg.0
0x1c07  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1c0c  callvirt instance string Microsoft.BIServer.Configuration.WebConfigFile::GetLoginUrl()
0x1c11  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_LoginUrl(string value)
0x1c16  dup
0x1c17  ldarg.0
0x1c18  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1c1d  callvirt instance string Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieName()
0x1c22  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_FormsCookieName(string value)
0x1c27  dup
0x1c28  ldarg.0
0x1c29  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1c2e  callvirt instance int32 Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieTimeoutMinutes()
0x1c33  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_FormsCookieTimeoutInMinutes(int32 value)
0x1c38  dup
0x1c39  ldarg.0
0x1c3a  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1c3f  callvirt instance bool Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookieSlidingExpiration()
0x1c44  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_FormsCookieSlidingExpiration(bool value)
0x1c49  dup
0x1c4a  ldarg.0
0x1c4b  ldfld    class Microsoft.BIServer.Configuration.WebConfigFile Microsoft.BIServer.Configuration.ConfigReader::_webConfigFile
0x1c50  callvirt instance string Microsoft.BIServer.Configuration.WebConfigFile::GetFormsCookiePath()
0x1c55  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_FormsCookiePath(string value)
0x1c5a  dup
0x1c5b  ldarg.0
0x1c5c  call     instance valuetype Microsoft.BIServer.Configuration.AuthenticationType Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationMode()
0x1c61  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_AuthenticationMode(valuetype Microsoft.BIServer.Configuration.AuthenticationType value)
0x1c66  dup
0x1c67  ldarg.0
0x1c68  call     instance valuetype Microsoft.BIServer.Configuration.AuthenticationTypes Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationTypes()
0x1c6d  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_AuthenticationTypes(valuetype Microsoft.BIServer.Configuration.AuthenticationTypes value)
0x1c72  dup
0x1c73  ldarg.0
0x1c74  call     instance class [System]System.Collections.Specialized.StringCollection Microsoft.BIServer.Configuration.ConfigReader::GetPassthroughCookies()
0x1c79  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_PassthroughCookies(class [System]System.Collections.Specialized.StringCollection value)
0x1c7e  dup
0x1c7f  ldarg.0
0x1c80  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class Microsoft.BIServer.Configuration.Extension> Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationExtensions()
0x1c85  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_AuthenticationExtensions(class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class Microsoft.BIServer.Configuration.Extension> value)
0x1c8a  dup
0x1c8b  ldarg.0
0x1c8c  call     instance valuetype Microsoft.BIServer.Configuration.AuthenticationTypes Microsoft.BIServer.Configuration.ConfigReader::GetAuthenticationTypes()
0x1c91  call     valuetype [System]System.Net.AuthenticationSchemes Microsoft.BIServer.Configuration.ConfigReader::Convert(valuetype Microsoft.BIServer.Configuration.AuthenticationTypes authenticationTypes)
0x1c96  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_AuthenticationSchemes(valuetype [System]System.Net.AuthenticationSchemes value)
0x1c9b  dup
0x1c9c  ldarg.0
0x1c9d  call     instance valuetype Microsoft.BIServer.Configuration.LogonType Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationLogonType()
0x1ca2  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_BasicAuthenticationLogonType(valuetype Microsoft.BIServer.Configuration.LogonType value)
0x1ca7  dup
0x1ca8  ldarg.0
0x1ca9  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationDomain()
0x1cae  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_BasicAuthenticationDomain(string value)
0x1cb3  dup
0x1cb4  ldarg.0
0x1cb5  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetBasicAuthenticationRealm()
0x1cba  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_BasicAuthenticationRealm(string value)
0x1cbf  dup
0x1cc0  ldarg.0
0x1cc1  call     instance bool Microsoft.BIServer.Configuration.ConfigReader::GetAuthPersistence()
0x1cc6  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_AuthPersistence(bool value)
0x1ccb  dup
0x1ccc  ldarg.0
0x1ccd  ldstr    aMaxactivereqfo// "MaxActiveReqForOneUser"
0x1cd2  ldc.i4.s 0x14
0x1cd4  ldc.i4.1
0x1cd5  ldc.i4   0x7FFFFFFF
0x1cda  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSettingWithValidation(string key, int32 defaultValue, int32 minValue, [opt] int32 maxValue)
0x1cdf  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_MaxActiveReqForOneUser(int32 value)
0x1ce4  dup
0x1ce5  ldarg.0
0x1ce6  ldstr    aReportserverwe// "ReportServerWebService"
0x1ceb  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.BIServer.Configuration.ConfigReader::GetApplicationHostUrls(string applicationName)
0x1cf0  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_ReportServerUrls(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> value)
0x1cf5  dup
0x1cf6  ldarg.0
0x1cf7  ldstr    aReportserverwe_0// "ReportServerWebApp"
0x1cfc  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.BIServer.Configuration.ConfigReader::GetApplicationHostUrls(string applicationName)
0x1d01  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_WebAppUrls(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> value)
0x1d06  dup
0x1d07  ldarg.0
0x1d08  ldstr    aReportserverwe// "ReportServerWebService"
0x1d0d  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetApplicationVirtualServerDirectory(string applicationName)
0x1d12  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_ReportServerVirtualDirectory(string value)
0x1d17  dup
0x1d18  ldarg.0
0x1d19  ldstr    aReportserverwe_0// "ReportServerWebApp"
0x1d1e  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetApplicationVirtualServerDirectory(string applicationName)
0x1d23  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_ReportServerWebAppVirtualDirectory(string value)
0x1d28  dup
0x1d29  ldarg.0
0x1d2a  call     instance class Microsoft.BIServer.Configuration.MachineKeySettings Microsoft.BIServer.Configuration.ConfigReader::GetMachineKeys()
0x1d2f  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_MachineKey(class Microsoft.BIServer.Configuration.MachineKeySettings value)
0x1d34  dup
0x1d35  ldarg.0
0x1d36  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetReportServerUrl()
0x1d3b  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_ReportServerUrlOverride(string value)
0x1d40  dup
0x1d41  ldarg.0
0x1d42  call     instance string Microsoft.BIServer.Configuration.ConfigReader::GetUrlRoot()
0x1d47  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_PortalUrlOverride(string value)
0x1d4c  dup
0x1d4d  ldarg.0
0x1d4e  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::GetSecureConnectionLevel()
0x1d53  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_SecureConnectionLevel(int32 value)
0x1d58  dup
0x1d59  ldarg.0
0x1d5a  call     instance class Microsoft.BIServer.Configuration.ServiceSettings Microsoft.BIServer.Configuration.ConfigReader::GetServiceSettings()
0x1d5f  callvirt instance void Microsoft.BIServer.Configuration.ServerConfiguration::set_Service(class Microsoft.BIServer.Configuration.ServiceSettings value)
0x1d64  ret
```
