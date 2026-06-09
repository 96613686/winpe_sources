# Microsoft.Reporting.WebForms.WebRequestHelper::GetServerUrlAccessObject

- ea: `0x22b90`
- end: `0x22c7b`
- name: `Microsoft.Reporting.WebForms.WebRequestHelper::GetServerUrlAccessObject`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x22b90`
- `0x22c80`

## string_xrefs

- `0x22c20`: `rs:TrustedUserToken`

## pseudocode

```c

```

## disassembly

```asm
0x22b90  ldarg.0
0x22b91  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0x22b96  castclass [System]System.Net.HttpWebRequest
0x22b9b  stloc.0
0x22b9c  ldloc.0
0x22b9d  ldarg.2
0x22b9e  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0x22ba3  ldloc.0
0x22ba4  ldarg.1
0x22ba5  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0x22baa  ldarg.s  7
0x22bac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22bb1  brtrue.s loc_22BD6
0x22bb3  ldloc.0
0x22bb4  ldnull
0x22bb5  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0x22bba  ldloc.0
0x22bbb  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x22bc0  ldstr    aAuthorization// "Authorization"
0x22bc5  ldstr    aBearer0// "Bearer {0}"
0x22bca  ldarg.s  7
0x22bcc  call     string [mscorlib]System.String::Format(string, object)
0x22bd1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x22bd6  ldloc.0
0x22bd7  ldarg.3
0x22bd8  ldarg.s  4
0x22bda  ldarg.s  5
0x22bdc  call     void Microsoft.Reporting.WebForms.WebRequestHelper::SetRequestHeaders(class [System]System.Net.HttpWebRequest request, class [System]System.Net.Cookie formsAuthCookie, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> headers, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Net.Cookie> cookies)
0x22be1  ldarg.s  8
0x22be3  brfalse  loc_22C79
0x22be8  ldarg.s  6
0x22bea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22bef  brtrue   loc_22C79
0x22bf4  ldarg.s  8
0x22bf6  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x22bfb  stloc.1
0x22bfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22c01  ldstr    a0123// "{0}={1}&{2}={3}"
0x22c06  ldc.i4.4
0x22c07  newarr   [mscorlib]System.Object
0x22c0c  dup
0x22c0d  ldc.i4.0
0x22c0e  ldstr    aRsTrustedusern// "rs:TrustedUserName"
0x22c13  stelem.ref
0x22c14  dup
0x22c15  ldc.i4.1
0x22c16  ldarg.s  6
0x22c18  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.UrlUtil::UrlEncode(string)
0x22c1d  stelem.ref
0x22c1e  dup
0x22c1f  ldc.i4.2
0x22c20  ldstr    aRsTrustedusert// "rs:TrustedUserToken"
0x22c25  stelem.ref
0x22c26  dup
0x22c27  ldc.i4.3
0x22c28  ldloc.1
0x22c29  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.UrlUtil::UrlEncode(string)
0x22c2e  stelem.ref
0x22c2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22c34  stloc.2
0x22c35  ldloc.0
0x22c36  ldstr    aPost// "POST"
0x22c3b  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x22c40  ldloc.0
0x22c41  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x22c46  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x22c4b  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x22c50  ldloc.2
0x22c51  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x22c56  stloc.3
0x22c57  ldloc.0
0x22c58  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x22c5d  stloc.s  4
0x22c5f  ldloc.s  4
0x22c61  ldloc.3
0x22c62  ldc.i4.0
0x22c63  ldloc.3
0x22c64  ldlen
0x22c65  conv.i4
0x22c66  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x22c6b  leave.s  loc_22C79
0x22c6d  ldloc.s  4
0x22c6f  brfalse.s loc_22C78
0x22c71  ldloc.s  4
0x22c73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22c78  endfinally
0x22c79  ldloc.0
0x22c7a  ret
```
