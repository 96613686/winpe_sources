# Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteExceptionAsHtml

- ea: `0x38ea0`
- end: `0x3906c`
- name: `Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteExceptionAsHtml`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x38cf0`

## callees

- `0x38ea0`
- `0x39070`
- `0x39080`
- `0x39090`
- `0x390a0`
- `0x390e0`

## string_xrefs

- `0x38f9c`: `A:link {FONT-SIZE: 10pt; FONT-FAMILY:'Segoe UI',Tahoma,Verdana,sans-serif; COLOR:#3366CC; TEXT-DECORATION:none}`

## pseudocode

```c

```

## disassembly

```asm
0x38ea0  ldarg.0
0x38ea1  ldfld    class [System.Web]System.Web.HttpResponse Microsoft.ReportingServices.Common.ErrorResponseWriter::m_response
0x38ea6  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.HttpResponse::get_Output()
0x38eab  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x38eb0  stloc.0
0x38eb1  ldloc.0
0x38eb2  ldc.i4.s 0x2B
0x38eb4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38eb9  ldloc.0
0x38eba  ldc.i4.s 0x29
0x38ebc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38ec1  ldloc.0
0x38ec2  ldc.i4.s 0x59
0x38ec4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38ec9  ldloc.0
0x38eca  ldarg.0
0x38ecb  callvirt instance string Microsoft.ReportingServices.Common.ErrorResponseWriter::get_ProductName()
0x38ed0  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38ed5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x38eda  ldloc.0
0x38edb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x38ee0  ldloc.0
0x38ee1  ldstr    aGenerator// "Generator"
0x38ee6  ldarg.0
0x38ee7  ldfld    string Microsoft.ReportingServices.Common.ErrorResponseWriter::m_generator
0x38eec  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteMetaTag(class [System.Web]System.Web.UI.HtmlTextWriter hw, string name, string content)
0x38ef1  ldloc.0
0x38ef2  ldstr    aHttpStatus// "HTTP Status"
0x38ef7  ldarg.0
0x38ef8  ldflda   int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::m_httpStatusCode
0x38efd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38f02  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x38f07  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteMetaTag(class [System.Web]System.Web.UI.HtmlTextWriter hw, string name, string content)
0x38f0c  ldloc.0
0x38f0d  ldstr    aProductlocalei// "ProductLocaleID"
0x38f12  ldarg.0
0x38f13  ldflda   int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::m_productLocaleId
0x38f18  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38f1d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x38f22  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteMetaTag(class [System.Web]System.Web.UI.HtmlTextWriter hw, string name, string content)
0x38f27  ldloc.0
0x38f28  ldstr    aCountrylocalei// "CountryLocaleID"
0x38f2d  ldarg.0
0x38f2e  ldflda   int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::m_countryLocaleId
0x38f33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38f38  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x38f3d  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteMetaTag(class [System.Web]System.Web.UI.HtmlTextWriter hw, string name, string content)
0x38f42  ldarg.0
0x38f43  ldfld    class [mscorlib]System.Exception Microsoft.ReportingServices.Common.ErrorResponseWriter::m_exception
0x38f48  brfalse.s loc_38F67
0x38f4a  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsClientLocal()
0x38f4f  brfalse.s loc_38F67
0x38f51  ldloc.0
0x38f52  ldstr    aStacktrace// "StackTrace"
0x38f57  ldarg.0
0x38f58  ldfld    class [mscorlib]System.Exception Microsoft.ReportingServices.Common.ErrorResponseWriter::m_exception
0x38f5d  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x38f62  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteMetaTag(class [System.Web]System.Web.UI.HtmlTextWriter hw, string name, string content)
0x38f67  ldloc.0
0x38f68  ldc.i4.s 0x4F
0x38f6a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38f6f  ldloc.0
0x38f70  ldstr    aBodyFontFamily// "BODY {FONT-FAMILY:'Segoe UI',Tahoma,Ver"...
0x38f75  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38f7a  ldloc.0
0x38f7b  ldstr    aH1FontFamilySe// "H1 {FONT-FAMILY:'Segoe UI',Tahoma,Verda"...
0x38f80  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38f85  ldloc.0
0x38f86  ldstr    aLiFontFamilySe// "LI {FONT-FAMILY:'Segoe UI',Tahoma,Verda"...
0x38f8b  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38f90  ldloc.0
0x38f91  ldstr    aProductinfoFon// ".ProductInfo {FONT-FAMILY:'Segoe UI',Ta"...
0x38f96  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38f9b  ldloc.0
0x38f9c  ldstr    aALinkFontSize1// "A:link {FONT-SIZE: 10pt; FONT-FAMILY:'S"...
0x38fa1  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38fa6  ldloc.0
0x38fa7  ldstr    aAHoverFontSize// "A:hover {FONT-SIZE: 10pt; FONT-FAMILY:'"...
0x38fac  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38fb1  ldloc.0
0x38fb2  ldstr    aAVisitedFontSi// "A:visited {FONT-SIZE: 10pt; FONT-FAMILY"...
0x38fb7  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38fbc  ldloc.0
0x38fbd  ldstr    aAVisitedHoverF// "A:visited:hover {FONT-SIZE: 10pt; FONT-"...
0x38fc2  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x38fc7  ldloc.0
0x38fc8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x38fcd  ldloc.0
0x38fce  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x38fd3  ldloc.0
0x38fd4  ldc.i4.4
0x38fd5  ldstr    aWhite// "white"
0x38fda  ldc.i4.0
0x38fdb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string, bool)
0x38fe0  ldloc.0
0x38fe1  ldc.i4.s 0xC
0x38fe3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38fe8  ldloc.0
0x38fe9  ldc.i4.s 0x23
0x38feb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x38ff0  ldloc.0
0x38ff1  ldarg.0
0x38ff2  callvirt instance string Microsoft.ReportingServices.Common.ErrorResponseWriter::get_ErrorPageTitle()
0x38ff7  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x38ffc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39001  ldloc.0
0x39002  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteHorizontalLine(class [System.Web]System.Web.UI.HtmlTextWriter hw)
0x39007  ldloc.0
0x39008  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3900d  ldarg.0
0x3900e  ldloc.0
0x3900f  callvirt instance int32 Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteHtmlErrorMessage(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x39014  stloc.1
0x39015  ldc.i4.0
0x39016  stloc.2
0x39017  br.s     loc_39023
0x39019  ldloc.0
0x3901a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3901f  ldloc.2
0x39020  ldc.i4.1
0x39021  add
0x39022  stloc.2
0x39023  ldloc.2
0x39024  ldloc.1
0x39025  blt.s    loc_39019
0x39027  ldloc.0
0x39028  call     void Microsoft.ReportingServices.Common.ErrorResponseWriter::WriteHorizontalLine(class [System.Web]System.Web.UI.HtmlTextWriter hw)
0x3902d  ldloc.0
0x3902e  ldc.i4.s 0xA
0x39030  ldstr    aProductinfo// "ProductInfo"
0x39035  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x3903a  ldloc.0
0x3903b  ldc.i4.s 0x4C
0x3903d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x39042  ldloc.0
0x39043  ldarg.0
0x39044  callvirt instance string Microsoft.ReportingServices.Common.ErrorResponseWriter::get_ProductName()
0x39049  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3904e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x39053  ldloc.0
0x39054  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x39059  ldloc.0
0x3905a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3905f  ldloc.0
0x39060  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x39065  ldloc.0
0x39066  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x3906b  ret
```
