# RSErrorResponseWriter::WriteHtmlErrorMessage

- ea: `0x3c8d0`
- end: `0x3ca4b`
- name: `RSErrorResponseWriter::WriteHtmlErrorMessage`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x35840`
- `0x38ce0`
- `0x3c8d0`

## string_xrefs

- `0x3c9af`: `noopener noreferrer`

## pseudocode

```c

```

## disassembly

```asm
0x3c8d0  ldc.i4.0
0x3c8d1  stloc.0
0x3c8d2  ldarg.0
0x3c8d3  call     instance class [mscorlib]System.Exception Microsoft.ReportingServices.Common.ErrorResponseWriter::get_ExceptionToDisplay()
0x3c8d8  brfalse  loc_3CA22
0x3c8dd  ldarg.0
0x3c8de  call     instance class [mscorlib]System.Exception Microsoft.ReportingServices.Common.ErrorResponseWriter::get_ExceptionToDisplay()
0x3c8e3  stloc.1
0x3c8e4  br       loc_3CA1A
0x3c8e9  ldc.i4.0
0x3c8ea  stloc.2
0x3c8eb  ldloc.1
0x3c8ec  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x3c8f1  brfalse.s loc_3C902
0x3c8f3  ldloc.1
0x3c8f4  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3c8f9  brfalse.s loc_3C902
0x3c8fb  ldloc.1
0x3c8fc  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3c901  stloc.1
0x3c902  ldloc.1
0x3c903  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x3c908  stloc.3
0x3c909  ldarg.1
0x3c90a  ldc.i4.s 0x5D
0x3c90c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x3c911  ldarg.1
0x3c912  ldc.i4.s 0x35
0x3c914  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x3c919  ldloc.3
0x3c91a  brfalse  loc_3C9D3
0x3c91f  ldloc.1
0x3c920  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3c925  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x3c92a  stloc.s  4
0x3c92c  ldloc.s  4
0x3c92e  brfalse.s loc_3C945
0x3c930  ldloc.3
0x3c931  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x3c936  ldloc.s  4
0x3c938  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x3c93d  bne.un.s loc_3C945
0x3c93f  ldloc.s  4
0x3c941  stloc.1
0x3c942  ldloc.s  4
0x3c944  stloc.3
0x3c945  ldarg.1
0x3c946  ldloc.1
0x3c947  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3c94c  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3c951  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c956  ldarg.1
0x3c957  ldstr    a0_4// " ({0}) "
0x3c95c  ldloc.3
0x3c95d  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x3c962  stloc.s  5
0x3c964  ldloca.s 5
0x3c966  constrained. [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x3c96c  callvirt instance string [mscorlib]System.Object::ToString()
0x3c971  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3c976  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x3c97b  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x3c980  brfalse  loc_3CA06
0x3c985  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x3c98a  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_DisplayErrorLink()
0x3c98f  brfalse.s loc_3CA06
0x3c991  ldarg.1
0x3c992  ldc.i4.s 0x10
0x3c994  ldloc.3
0x3c995  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ExceptionLevelHelpLink()
0x3c99a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x3c99f  ldarg.1
0x3c9a0  ldc.i4.s 0x21
0x3c9a2  ldstr    aBlank_0// "_blank"
0x3c9a7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x3c9ac  ldarg.1
0x3c9ad  ldc.i4.s 0x31
0x3c9af  ldstr    aNoopenerNorefe// "noopener noreferrer"
0x3c9b4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x3c9b9  ldarg.1
0x3c9ba  ldc.i4.1
0x3c9bb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x3c9c0  ldarg.1
0x3c9c1  call     string Microsoft.ReportingServices.WebServer.WebServRes::get_HelpLinkText()
0x3c9c6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c9cb  ldarg.1
0x3c9cc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3c9d1  br.s     loc_3CA06
0x3c9d3  call     bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::get_EnableRemoteErrors()
0x3c9d8  brtrue.s loc_3C9E1
0x3c9da  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.WebRequestUtil::IsClientLocal()
0x3c9df  brfalse.s loc_3C9F4
0x3c9e1  ldarg.1
0x3c9e2  ldloc.1
0x3c9e3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3c9e8  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3c9ed  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3c9f2  br.s     loc_3CA06
0x3c9f4  ldarg.1
0x3c9f5  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_ErrorNotVisibleOnRemoteBrowsers()
0x3c9fa  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3c9ff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3ca04  ldc.i4.1
0x3ca05  stloc.2
0x3ca06  ldarg.1
0x3ca07  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3ca0c  ldloc.2
0x3ca0d  brtrue.s loc_3CA49
0x3ca0f  ldloc.1
0x3ca10  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3ca15  stloc.1
0x3ca16  ldloc.0
0x3ca17  ldc.i4.1
0x3ca18  add
0x3ca19  stloc.0
0x3ca1a  ldloc.1
0x3ca1b  brtrue   loc_3C8E9
0x3ca20  br.s     loc_3CA49
0x3ca22  ldarg.1
0x3ca23  ldc.i4.s 0x5D
0x3ca25  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x3ca2a  ldarg.1
0x3ca2b  ldc.i4.s 0x35
0x3ca2d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x3ca32  ldarg.1
0x3ca33  ldarg.0
0x3ca34  ldfld    string RSErrorResponseWriter::m_optionalMessage
0x3ca39  call     string [System.Web]System.Web.HttpUtility::HtmlEncode(string)
0x3ca3e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x3ca43  ldarg.1
0x3ca44  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x3ca49  ldloc.0
0x3ca4a  ret
```
