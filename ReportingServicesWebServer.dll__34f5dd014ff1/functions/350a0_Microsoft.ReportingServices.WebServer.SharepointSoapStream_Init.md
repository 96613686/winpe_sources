# Microsoft.ReportingServices.WebServer.SharepointSoapStream::Init

- ea: `0x350a0`
- end: `0x3525c`
- name: `Microsoft.ReportingServices.WebServer.SharepointSoapStream::Init`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x346d0`
- `0x346f0`
- `0x34700`
- `0x350a0`

## string_xrefs

- `0x351eb`: `rs:TrustedUserToken`
- `0x3520c`: `Failed to convert token from Base64 string`
- `0x3523e`: `Unexpected error encountered in sharepoint SOAP extension!`

## pseudocode

```c

```

## disassembly

```asm
0x350a0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x350a5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x350aa  stloc.0
0x350ab  ldnull
0x350ac  stloc.1
0x350ad  ldloc.0
0x350ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x350b3  ldstr    aSharepointprea// "SharepointPreambleLength"
0x350b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x350bd  stloc.2
0x350be  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x350c3  ldloc.2
0x350c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x350c9  ldc.i4.0
0x350ca  ceq
0x350cc  ldstr    aSharepointsoap_0// "SharepointSoapStream.Init(): !string.Is"...
0x350d1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x350d6  ldarg.0
0x350d7  newobj   instance void Microsoft.ReportingServices.WebServer.TrustedUserHeader::.ctor()
0x350dc  stfld    class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_trustedUserHeader
0x350e1  ldloc.2
0x350e2  ldarg.0
0x350e3  ldflda   int64 Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_preambleLength
0x350e8  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0x350ed  brtrue.s loc_350F6
0x350ef  ldloc.2
0x350f0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SoapExtensionInvalidPreambleLengthException::.ctor(string)
0x350f5  throw
0x350f6  ldarg.0
0x350f7  ldfld    int64 Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_preambleLength
0x350fc  ldarg.0
0x350fd  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_stream
0x35102  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x35107  ble.s    loc_35115
0x35109  ldarg.0
0x3510a  ldfld    int64 Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_preambleLength
0x3510f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SoapExtensionInvalidPreambleLengthException::.ctor(int64)
0x35114  throw
0x35115  ldarg.0
0x35116  ldfld    int64 Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_preambleLength
0x3511b  conv.ovf.i
0x3511c  newarr   [mscorlib]System.Byte
0x35121  stloc.3
0x35122  ldarg.0
0x35123  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_stream
0x35128  ldloc.3
0x35129  ldc.i4.0
0x3512a  ldloc.3
0x3512b  ldlen
0x3512c  conv.i4
0x3512d  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x35132  pop
0x35133  ldloc.0
0x35134  callvirt instance class [mscorlib]System.Text.Encoding [System.Web]System.Web.HttpRequest::get_ContentEncoding()
0x35139  ldloc.3
0x3513a  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x3513f  stloc.1
0x35140  ldc.i4.0
0x35141  stloc.s  4
0x35143  br       loc_3521E
0x35148  ldloc.1
0x35149  ldc.i4.s 0x26
0x3514b  ldloc.s  4
0x3514d  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x35152  stloc.s  5
0x35154  ldloc.s  5
0x35156  ldc.i4.m1
0x35157  bne.un.s loc_35161
0x35159  ldloc.1
0x3515a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3515f  stloc.s  5
0x35161  ldloc.1
0x35162  ldc.i4.s 0x3D
0x35164  ldloc.s  4
0x35166  ldloc.s  5
0x35168  ldloc.s  4
0x3516a  sub
0x3516b  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32, int32)
0x35170  stloc.s  6
0x35172  ldloc.s  6
0x35174  ldc.i4.m1
0x35175  bne.un.s loc_3519F
0x35177  ldnull
0x35178  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3517d  ldstr    aFailedToFindSt// "Failed to find = starting from index {0"...
0x35182  ldloc.s  4
0x35184  box      [mscorlib]System.Int32
0x35189  ldloc.s  5
0x3518b  ldloc.s  4
0x3518d  sub
0x3518e  box      [mscorlib]System.Int32
0x35193  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x35198  ldloc.1
0x35199  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SoapExtensionInvalidPreambleException::.ctor(class [mscorlib]System.Exception, string, string)
0x3519e  throw
0x3519f  ldloc.1
0x351a0  ldloc.s  4
0x351a2  ldloc.s  6
0x351a4  ldloc.s  4
0x351a6  sub
0x351a7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x351ac  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x351b1  stloc.s  7
0x351b3  ldloc.1
0x351b4  ldloc.s  6
0x351b6  ldc.i4.1
0x351b7  add
0x351b8  ldloc.s  5
0x351ba  ldloc.s  6
0x351bc  sub
0x351bd  ldc.i4.1
0x351be  sub
0x351bf  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x351c4  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x351c9  stloc.s  8
0x351cb  ldloc.s  7
0x351cd  ldstr    aRsTrustedusern// "rs:TrustedUserName"
0x351d2  ldc.i4.5
0x351d3  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x351d8  brfalse.s loc_351E9
0x351da  ldarg.0
0x351db  ldfld    class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_trustedUserHeader
0x351e0  ldloc.s  8
0x351e2  callvirt instance void Microsoft.ReportingServices.WebServer.TrustedUserHeader::set_UserName(string value)
0x351e7  br.s     loc_35218
0x351e9  ldloc.s  7
0x351eb  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x351f0  ldc.i4.5
0x351f1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x351f6  brfalse.s loc_35218
0x351f8  ldarg.0
0x351f9  ldfld    class Microsoft.ReportingServices.WebServer.TrustedUserHeader Microsoft.ReportingServices.WebServer.SharepointSoapStream::m_trustedUserHeader
0x351fe  ldloc.s  8
0x35200  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x35205  callvirt instance void Microsoft.ReportingServices.WebServer.TrustedUserHeader::set_UserToken(unsigned int8[] value)
0x3520a  leave.s  loc_35218
0x3520c  ldstr    aFailedToConver// "Failed to convert token from Base64 str"...
0x35211  ldloc.1
0x35212  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SoapExtensionInvalidPreambleException::.ctor(class [mscorlib]System.Exception, string, string)
0x35217  throw
0x35218  ldloc.s  5
0x3521a  ldc.i4.1
0x3521b  add
0x3521c  stloc.s  4
0x3521e  ldloc.s  4
0x35220  ldloc.1
0x35221  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35226  blt      loc_35148
0x3522b  leave.s  loc_3525B
0x3522d  stloc.s  9
0x3522f  ldloc.s  9
0x35231  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x35236  stloc.s  0xA
0x35238  ldloc.s  0xA
0x3523a  brtrue.s loc_35249
0x3523c  ldloc.s  9
0x3523e  ldstr    aUnexpectedErro// "Unexpected error encountered in sharepo"...
0x35243  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x35248  throw
0x35249  ldloc.s  0xA
0x3524b  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_RecycleOnSevereErrors()
0x35250  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_EnableRemoteErrors()
0x35255  call     class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ExceptionExtensions::WebServerToSoapException(class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException, bool, bool)
0x3525a  throw
0x3525b  ret
```
