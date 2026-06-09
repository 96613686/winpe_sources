# Microsoft.SharePoint.ServerStub.Utilities.SPWOPIPropertiesServerStub::WritePropertiesAsJson

- ea: `0xa2ef0`
- end: `0xa3061`
- name: `Microsoft.SharePoint.ServerStub.Utilities.SPWOPIPropertiesServerStub::WritePropertiesAsJson`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa2ef0`

## string_xrefs

- `0xa2f05`: `AccessToken`
- `0xa2f11`: `AccessToken`
- `0xa2f1c`: `AccessToken`
- `0xa2f34`: `AccessToken`
- `0xa2f3f`: `AccessTokenTtl`
- `0xa2f4b`: `AccessTokenTtl`
- `0xa2f56`: `AccessTokenTtl`
- `0xa2f6e`: `AccessTokenTtl`

## pseudocode

```c

```

## disassembly

```asm
0xa2ef0  ldarg.2
0xa2ef1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties
0xa2ef6  stloc.0
0xa2ef7  ldloc.0
0xa2ef8  brtrue.s loc_A2EFB
0xa2efa  ret
0xa2efb  ldarg.0
0xa2efc  ldarg.1
0xa2efd  ldarg.2
0xa2efe  ldarg.3
0xa2eff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f04  ldarg.0
0xa2f05  ldstr    aAccesstoken// "AccessToken"
0xa2f0a  ldarg.3
0xa2f0b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f10  ldarg.1
0xa2f11  ldstr    aAccesstoken// "AccessToken"
0xa2f16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa2f1b  ldarg.3
0xa2f1c  ldstr    aAccesstoken// "AccessToken"
0xa2f21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa2f26  ldarg.1
0xa2f27  ldloc.0
0xa2f28  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_AccessToken()
0xa2f2d  ldarg.3
0xa2f2e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f33  ldarg.3
0xa2f34  ldstr    aAccesstoken// "AccessToken"
0xa2f39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa2f3e  ldarg.0
0xa2f3f  ldstr    aAccesstokenttl// "AccessTokenTtl"
0xa2f44  ldarg.3
0xa2f45  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f4a  ldarg.1
0xa2f4b  ldstr    aAccesstokenttl// "AccessTokenTtl"
0xa2f50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa2f55  ldarg.3
0xa2f56  ldstr    aAccesstokenttl// "AccessTokenTtl"
0xa2f5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa2f60  ldarg.1
0xa2f61  ldloc.0
0xa2f62  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_AccessTokenTtl()
0xa2f67  ldarg.3
0xa2f68  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f6d  ldarg.3
0xa2f6e  ldstr    aAccesstokenttl// "AccessTokenTtl"
0xa2f73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa2f78  ldarg.0
0xa2f79  ldstr    aAppiconurl// "AppIconUrl"
0xa2f7e  ldarg.3
0xa2f7f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2f84  ldarg.1
0xa2f85  ldstr    aAppiconurl// "AppIconUrl"
0xa2f8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa2f8f  ldarg.3
0xa2f90  ldstr    aAppiconurl// "AppIconUrl"
0xa2f95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa2f9a  ldarg.1
0xa2f9b  ldloc.0
0xa2f9c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_AppIconUrl()
0xa2fa1  ldarg.3
0xa2fa2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2fa7  ldarg.3
0xa2fa8  ldstr    aAppiconurl// "AppIconUrl"
0xa2fad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa2fb2  ldarg.0
0xa2fb3  ldstr    aErrormessageto// "ErrorMessageToDisplay"
0xa2fb8  ldarg.3
0xa2fb9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2fbe  ldarg.1
0xa2fbf  ldstr    aErrormessageto// "ErrorMessageToDisplay"
0xa2fc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa2fc9  ldarg.3
0xa2fca  ldstr    aErrormessageto// "ErrorMessageToDisplay"
0xa2fcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa2fd4  ldarg.1
0xa2fd5  ldloc.0
0xa2fd6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_ErrorMessageToDisplay()
0xa2fdb  ldarg.3
0xa2fdc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2fe1  ldarg.3
0xa2fe2  ldstr    aErrormessageto// "ErrorMessageToDisplay"
0xa2fe7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa2fec  ldarg.0
0xa2fed  ldstr    aRedirecturl// "RedirectUrl"
0xa2ff2  ldarg.3
0xa2ff3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa2ff8  ldarg.1
0xa2ff9  ldstr    aRedirecturl// "RedirectUrl"
0xa2ffe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa3003  ldarg.3
0xa3004  ldstr    aRedirecturl// "RedirectUrl"
0xa3009  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa300e  ldarg.1
0xa300f  ldloc.0
0xa3010  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_RedirectUrl()
0xa3015  ldarg.3
0xa3016  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa301b  ldarg.3
0xa301c  ldstr    aRedirecturl// "RedirectUrl"
0xa3021  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa3026  ldarg.0
0xa3027  ldstr    aWebapplication_0// "WebApplicationUrl"
0xa302c  ldarg.3
0xa302d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3032  ldarg.1
0xa3033  ldstr    aWebapplication_0// "WebApplicationUrl"
0xa3038  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa303d  ldarg.3
0xa303e  ldstr    aWebapplication_0// "WebApplicationUrl"
0xa3043  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa3048  ldarg.1
0xa3049  ldloc.0
0xa304a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIProperties::get_WebApplicationUrl()
0xa304f  ldarg.3
0xa3050  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa3055  ldarg.3
0xa3056  ldstr    aWebapplication_0// "WebApplicationUrl"
0xa305b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa3060  ret
```
