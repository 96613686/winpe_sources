# System.Web.HttpRequest::FillInServerVariablesCollection

- ea: `0x1aab0`
- end: `0x1ad91`
- name: `System.Web.HttpRequest::FillInServerVariablesCollection`
- size: `737`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x26720`

## callees

- `0x1a860`
- `0x1a880`
- `0x1aa60`
- `0x1aa70`
- `0x1aa90`
- `0x1aab0`
- `0x1b710`
- `0x1b840`
- `0x1bfd0`
- `0x1c000`
- `0x31e10`
- `0x31e40`
- `0x31e60`
- `0x31f50`
- `0x32040`
- `0x320c0`
- `0x32200`
- `0x32220`
- `0x32610`

## string_xrefs

- `0x1aade`: `APPL_MD_PATH`
- `0x1aae9`: `APPL_PHYSICAL_PATH`
- `0x1ac1e`: `INSTANCE_META_PATH`
- `0x1ac3f`: `PATH_INFO`
- `0x1ac4b`: `PATH_TRANSLATED`
- `0x1acfd`: `SERVER_PROTOCOL`

## pseudocode

```c

```

## disassembly

```asm
0x1aab0  ldarg.0
0x1aab1  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1aab6  brtrue.s loc_1AAB9
0x1aab8  ret
0x1aab9  ldarg.0
0x1aaba  ldstr    aAllHttp// "ALL_HTTP"
0x1aabf  ldarg.0
0x1aac0  ldc.i4.0
0x1aac1  call     instance string System.Web.HttpRequest::CombineAllHeaders(bool asRaw)
0x1aac6  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1aacb  ldarg.0
0x1aacc  ldstr    aAllRaw// "ALL_RAW"
0x1aad1  ldarg.0
0x1aad2  ldc.i4.1
0x1aad3  call     instance string System.Web.HttpRequest::CombineAllHeaders(bool asRaw)
0x1aad8  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1aadd  ldarg.0
0x1aade  ldstr    aApplMdPath// "APPL_MD_PATH"
0x1aae3  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1aae8  ldarg.0
0x1aae9  ldstr    aApplPhysicalPa// "APPL_PHYSICAL_PATH"
0x1aaee  ldarg.0
0x1aaef  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1aaf4  callvirt instance string System.Web.HttpWorkerRequest::GetAppPathTranslated()
0x1aaf9  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1aafe  ldarg.0
0x1aaff  ldstr    aAuthType// "AUTH_TYPE"
0x1ab04  ldc.i4.1
0x1ab05  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ab0a  ldarg.0
0x1ab0b  ldstr    aAuthUser// "AUTH_USER"
0x1ab10  ldc.i4.2
0x1ab11  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ab16  ldarg.0
0x1ab17  ldstr    aAuthPassword// "AUTH_PASSWORD"
0x1ab1c  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab21  ldarg.0
0x1ab22  ldstr    aLogonUser// "LOGON_USER"
0x1ab27  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab2c  ldarg.0
0x1ab2d  ldstr    aRemoteUser// "REMOTE_USER"
0x1ab32  ldc.i4.2
0x1ab33  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ab38  ldarg.0
0x1ab39  ldstr    aCertCookie// "CERT_COOKIE"
0x1ab3e  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab43  ldarg.0
0x1ab44  ldstr    aCertFlags// "CERT_FLAGS"
0x1ab49  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab4e  ldarg.0
0x1ab4f  ldstr    aCertIssuer// "CERT_ISSUER"
0x1ab54  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab59  ldarg.0
0x1ab5a  ldstr    aCertKeysize// "CERT_KEYSIZE"
0x1ab5f  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab64  ldarg.0
0x1ab65  ldstr    aCertSecretkeys// "CERT_SECRETKEYSIZE"
0x1ab6a  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab6f  ldarg.0
0x1ab70  ldstr    aCertSerialnumb// "CERT_SERIALNUMBER"
0x1ab75  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab7a  ldarg.0
0x1ab7b  ldstr    aCertServerIssu// "CERT_SERVER_ISSUER"
0x1ab80  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab85  ldarg.0
0x1ab86  ldstr    aCertServerSubj// "CERT_SERVER_SUBJECT"
0x1ab8b  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab90  ldarg.0
0x1ab91  ldstr    aCertSubject// "CERT_SUBJECT"
0x1ab96  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ab9b  ldarg.0
0x1ab9c  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1aba1  ldc.i4.s 0xB
0x1aba3  callvirt instance string System.Web.HttpWorkerRequest::GetKnownRequestHeader(int32 index)
0x1aba8  stloc.0
0x1aba9  ldarg.0
0x1abaa  ldstr    aContentLength// "CONTENT_LENGTH"
0x1abaf  ldloc.0
0x1abb0  brtrue.s loc_1ABB9
0x1abb2  ldstr    a0// "0"
0x1abb7  br.s     loc_1ABBA
0x1abb9  ldloc.0
0x1abba  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1abbf  ldarg.0
0x1abc0  ldstr    aContentType// "CONTENT_TYPE"
0x1abc5  ldarg.0
0x1abc6  call     instance string System.Web.HttpRequest::get_ContentType()
0x1abcb  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1abd0  ldarg.0
0x1abd1  ldstr    aGatewayInterfa// "GATEWAY_INTERFACE"
0x1abd6  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1abdb  ldarg.0
0x1abdc  ldstr    aHttps// "HTTPS"
0x1abe1  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1abe6  ldarg.0
0x1abe7  ldstr    aHttpsKeysize// "HTTPS_KEYSIZE"
0x1abec  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1abf1  ldarg.0
0x1abf2  ldstr    aHttpsSecretkey// "HTTPS_SECRETKEYSIZE"
0x1abf7  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1abfc  ldarg.0
0x1abfd  ldstr    aHttpsServerIss// "HTTPS_SERVER_ISSUER"
0x1ac02  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ac07  ldarg.0
0x1ac08  ldstr    aHttpsServerSub// "HTTPS_SERVER_SUBJECT"
0x1ac0d  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ac12  ldarg.0
0x1ac13  ldstr    aInstanceId// "INSTANCE_ID"
0x1ac18  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ac1d  ldarg.0
0x1ac1e  ldstr    aInstanceMetaPa// "INSTANCE_META_PATH"
0x1ac23  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ac28  ldarg.0
0x1ac29  ldstr    aLocalAddr// "LOCAL_ADDR"
0x1ac2e  ldarg.0
0x1ac2f  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1ac34  callvirt instance string System.Web.HttpWorkerRequest::GetLocalAddress()
0x1ac39  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ac3e  ldarg.0
0x1ac3f  ldstr    aPathInfo// "PATH_INFO"
0x1ac44  ldc.i4.3
0x1ac45  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ac4a  ldarg.0
0x1ac4b  ldstr    aPathTranslated// "PATH_TRANSLATED"
0x1ac50  ldc.i4.4
0x1ac51  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ac56  ldarg.0
0x1ac57  ldstr    aQueryString// "QUERY_STRING"
0x1ac5c  ldc.i4.5
0x1ac5d  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ac62  ldarg.0
0x1ac63  ldstr    aRemoteAddr// "REMOTE_ADDR"
0x1ac68  ldarg.0
0x1ac69  call     instance string System.Web.HttpRequest::get_UserHostAddress()
0x1ac6e  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ac73  ldarg.0
0x1ac74  ldstr    aRemoteHost// "REMOTE_HOST"
0x1ac79  ldarg.0
0x1ac7a  call     instance string System.Web.HttpRequest::get_UserHostName()
0x1ac7f  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ac84  ldarg.0
0x1ac85  ldstr    aRemotePort// "REMOTE_PORT"
0x1ac8a  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ac8f  ldarg.0
0x1ac90  ldstr    aRequestMethod// "REQUEST_METHOD"
0x1ac95  ldarg.0
0x1ac96  call     instance string System.Web.HttpRequest::get_HttpMethod()
0x1ac9b  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1aca0  ldarg.0
0x1aca1  ldstr    aScriptName// "SCRIPT_NAME"
0x1aca6  ldc.i4.6
0x1aca7  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1acac  ldarg.0
0x1acad  ldstr    aServerName// "SERVER_NAME"
0x1acb2  ldarg.0
0x1acb3  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1acb8  callvirt instance string System.Web.HttpWorkerRequest::GetServerName()
0x1acbd  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1acc2  ldarg.0
0x1acc3  ldstr    aServerPort// "SERVER_PORT"
0x1acc8  ldarg.0
0x1acc9  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1acce  callvirt instance string System.Web.HttpWorkerRequest::GetLocalPortAsString()
0x1acd3  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1acd8  ldarg.0
0x1acd9  ldstr    aServerPortSecu// "SERVER_PORT_SECURE"
0x1acde  ldarg.0
0x1acdf  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1ace4  callvirt instance bool System.Web.HttpWorkerRequest::IsSecure()
0x1ace9  brtrue.s loc_1ACF2
0x1aceb  ldstr    a0// "0"
0x1acf0  br.s     loc_1ACF7
0x1acf2  ldstr    a1_0// "1"
0x1acf7  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1acfc  ldarg.0
0x1acfd  ldstr    aServerProtocol// "SERVER_PROTOCOL"
0x1ad02  ldarg.0
0x1ad03  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1ad08  callvirt instance string System.Web.HttpWorkerRequest::GetHttpVersion()
0x1ad0d  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ad12  ldarg.0
0x1ad13  ldstr    aServerSoftware// "SERVER_SOFTWARE"
0x1ad18  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name)
0x1ad1d  ldarg.0
0x1ad1e  ldstr    aUrl// "URL"
0x1ad23  ldc.i4.6
0x1ad24  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, valuetype System.Web.DynamicServerVariable var)
0x1ad29  ldc.i4.0
0x1ad2a  stloc.2
0x1ad2b  br.s     loc_1AD53
0x1ad2d  ldarg.0
0x1ad2e  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1ad33  ldloc.2
0x1ad34  callvirt instance string System.Web.HttpWorkerRequest::GetKnownRequestHeader(int32 index)
0x1ad39  stloc.3
0x1ad3a  ldloc.3
0x1ad3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ad40  brtrue.s loc_1AD4F
0x1ad42  ldarg.0
0x1ad43  ldloc.2
0x1ad44  call     string System.Web.HttpWorkerRequest::GetServerVariableNameFromKnownRequestHeaderIndex(int32 index)
0x1ad49  ldloc.3
0x1ad4a  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ad4f  ldloc.2
0x1ad50  ldc.i4.1
0x1ad51  add
0x1ad52  stloc.2
0x1ad53  ldloc.2
0x1ad54  ldc.i4.s 0x28
0x1ad56  blt.s    loc_1AD2D
0x1ad58  ldarg.0
0x1ad59  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpRequest::_wr
0x1ad5e  callvirt instance string[][] System.Web.HttpWorkerRequest::GetUnknownRequestHeaders()
0x1ad63  stloc.1
0x1ad64  ldloc.1
0x1ad65  brfalse.s loc_1AD90
0x1ad67  ldc.i4.0
0x1ad68  stloc.s  4
0x1ad6a  br.s     loc_1AD89
0x1ad6c  ldarg.0
0x1ad6d  ldloc.1
0x1ad6e  ldloc.s  4
0x1ad70  ldelem.ref
0x1ad71  ldc.i4.0
0x1ad72  ldelem.ref
0x1ad73  call     string System.Web.HttpRequest::ServerVariableNameFromHeader(string header)
0x1ad78  ldloc.1
0x1ad79  ldloc.s  4
0x1ad7b  ldelem.ref
0x1ad7c  ldc.i4.1
0x1ad7d  ldelem.ref
0x1ad7e  call     instance void System.Web.HttpRequest::AddServerVariableToCollection(string name, string value)
0x1ad83  ldloc.s  4
0x1ad85  ldc.i4.1
0x1ad86  add
0x1ad87  stloc.s  4
0x1ad89  ldloc.s  4
0x1ad8b  ldloc.1
0x1ad8c  ldlen
0x1ad8d  conv.i4
0x1ad8e  blt.s    loc_1AD6C
0x1ad90  ret
```
