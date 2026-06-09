# Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteError

- ea: `0x38cf0`
- end: `0x38e94`
- name: `Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteError`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x32830`

## callees

- `0x38cf0`
- `0x38ea0`

## string_xrefs

- `0x38d56`: `text/xml`
- `0x38de1`: `rsEvaluationCopyExpired`
- `0x38e66`: `SoapException required to write error response as XML`

## pseudocode

```c

```

## disassembly

```asm
0x38cf0  ldarg.0
0x38cf1  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38cf6  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x38cfb  ldarg.0
0x38cfc  ldfld    bool Microsoft.ReportingServices.Common.ErrorResponseWriter::m_headersSet
0x38d01  brtrue   loc_38D8D
0x38d06  ldarg.0
0x38d07  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38d0c  ldarg.0
0x38d0d  ldfld    int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusCode
0x38d12  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x38d17  ldarg.0
0x38d18  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusDescription
0x38d1d  brtrue.s loc_38D30
0x38d1f  ldarg.0
0x38d20  ldarg.0
0x38d21  ldfld    int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusCode
0x38d26  call     string [System.Web]System.Web.HttpWorkerRequest::GetStatusDescription(int32)
0x38d2b  stfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusDescription
0x38d30  ldarg.0
0x38d31  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38d36  ldarg.0
0x38d37  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusDescription
0x38d3c  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusDescription(string)
0x38d41  ldarg.0
0x38d42  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38d47  ldarg.0
0x38d48  ldfld    bool Microsoft.ReportingServices.Common.ErrorResponseWriter::m_errorResponseAsXml
0x38d4d  brtrue.s loc_38D56
0x38d4f  ldstr    aTextHtml// "text/html"
0x38d54  br.s     loc_38D5B
0x38d56  ldstr    aTextXml// "text/xml"
0x38d5b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x38d60  ldarg.0
0x38d61  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38d66  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x38d6b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0x38d70  leave.s  loc_38D8D
0x38d72  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x38d77  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x38d7c  ldstr    aHeadersset// "HeadersSet"
0x38d81  ldc.i4.1
0x38d82  box      [mscorlib]System.Boolean
0x38d87  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x38d8c  endfinally
0x38d8d  ldstr    aRsreportserver// "rsReportServerNotActivated"
0x38d92  ldarg.0
0x38d93  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_reportServerErrorCode
0x38d98  ldc.i4.5
0x38d99  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x38d9e  brfalse.s loc_38DB7
0x38da0  ldarg.0
0x38da1  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38da6  ldstr    aRsnotactivated// "RSNotActivated"
0x38dab  ldstr    aTrue// "true"
0x38db0  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x38db5  br.s     loc_38E09
0x38db7  ldstr    aRsreportserver_0// "rsReportServerDisabled"
0x38dbc  ldarg.0
0x38dbd  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_reportServerErrorCode
0x38dc2  ldc.i4.5
0x38dc3  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x38dc8  brfalse.s loc_38DE1
0x38dca  ldarg.0
0x38dcb  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38dd0  ldstr    aRsdisabled// "RSDisabled"
0x38dd5  ldstr    aTrue// "true"
0x38dda  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x38ddf  br.s     loc_38E09
0x38de1  ldstr    aRsevaluationco// "rsEvaluationCopyExpired"
0x38de6  ldarg.0
0x38de7  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_reportServerErrorCode
0x38dec  ldc.i4.5
0x38ded  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x38df2  brfalse.s loc_38E09
0x38df4  ldarg.0
0x38df5  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38dfa  ldstr    aRsexpired// "RSExpired"
0x38dff  ldstr    aTrue// "true"
0x38e04  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x38e09  ldarg.0
0x38e0a  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Common.ErrorResponseWriter::m_additionalHeaders
0x38e0f  brfalse.s loc_38E4F
0x38e11  ldc.i4.0
0x38e12  stloc.0
0x38e13  br.s     loc_38E41
0x38e15  ldarg.0
0x38e16  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38e1b  ldarg.0
0x38e1c  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Common.ErrorResponseWriter::m_additionalHeaders
0x38e21  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x38e26  ldloc.0
0x38e27  callvirt instance string [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::get_Item(int32)
0x38e2c  ldarg.0
0x38e2d  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Common.ErrorResponseWriter::m_additionalHeaders
0x38e32  ldloc.0
0x38e33  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(int32)
0x38e38  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x38e3d  ldloc.0
0x38e3e  ldc.i4.1
0x38e3f  add
0x38e40  stloc.0
0x38e41  ldloc.0
0x38e42  ldarg.0
0x38e43  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Common.ErrorResponseWriter::m_additionalHeaders
0x38e48  callvirt instance int32 [System]System.Collections.Specialized.NameObjectCollectionBase::get_Count()
0x38e4d  blt.s    loc_38E15
0x38e4f  ldarg.0
0x38e50  ldfld    bool Microsoft.ReportingServices.Common.ErrorResponseWriter::m_errorResponseAsXml
0x38e55  brfalse.s loc_38E8D
0x38e57  ldarg.0
0x38e58  ldfld    class [mscorlib]System.Exception Microsoft.ReportingServices.Common.ErrorResponseWriter::m_exception
0x38e5d  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x38e62  stloc.1
0x38e63  ldloc.1
0x38e64  brtrue.s loc_38E71
0x38e66  ldstr    aSoapexceptionR// "SoapException required to write error r"...
0x38e6b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x38e70  throw
0x38e71  ldarg.0
0x38e72  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38e77  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.HttpResponse::get_Output()
0x38e7c  ldloc.1
0x38e7d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x38e82  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x38e87  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x38e8c  ret
0x38e8d  ldarg.0
0x38e8e  call     instance void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteExceptionAsHtml()
0x38e93  ret
```
