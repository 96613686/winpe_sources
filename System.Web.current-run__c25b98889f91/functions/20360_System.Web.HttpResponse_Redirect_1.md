# System.Web.HttpResponse::Redirect_1

- ea: `0x20360`
- end: `0x204f4`
- name: `System.Web.HttpResponse::Redirect_1`
- size: `404`
- prototype: ``
- caller_count: `5`
- callee_count: `24`
- tags: ``

## callers

- `0x20230`
- `0x20240`
- `0x202a0`
- `0x20340`
- `0x20350`

## callees

- `0x16180`
- `0x18990`
- `0x1c460`
- `0x1dd70`
- `0x1f6e0`
- `0x1f980`
- `0x1fcb0`
- `0x20120`
- `0x20360`
- `0x20500`
- `0x207d0`
- `0x20e70`
- `0x210b0`
- `0x21270`
- `0x21330`
- `0x23060`
- `0x26030`
- `0x26080`
- `0x26280`
- `0x34fa0`
- `0x4fe30`
- `0x71c00`
- `0x728d0`
- `0x750e0`

## string_xrefs

- `0x204a3`: `<html><head><title>Object moved</title></head><body>\n`
- `0x204ae`: `<h2>Object moved to <a href="`

## pseudocode

```c

```

## disassembly

```asm
0x20360  ldarg.1
0x20361  brtrue.s loc_2036E
0x20363  ldstr    aUrl_0// "url"
0x20368  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2036d  throw
0x2036e  ldarg.1
0x2036f  ldc.i4.s 0xA
0x20371  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x20376  ldc.i4.0
0x20377  blt.s    loc_20389
0x20379  ldstr    aCannotRedirect// "Cannot_redirect_to_newline"
0x2037e  call     string System.Web.SR::GetString(string name)
0x20383  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x20388  throw
0x20389  ldarg.0
0x2038a  ldfld    bool System.Web.HttpResponse::_headersWritten
0x2038f  brfalse.s loc_203A1
0x20391  ldstr    aCannotRedirect_0// "Cannot_redirect_after_headers_sent"
0x20396  call     string System.Web.SR::GetString(string name)
0x2039b  newobj   instance void System.Web.HttpException::.ctor(string message)
0x203a0  throw
0x203a1  ldarg.0
0x203a2  ldfld    class System.Web.HttpContext System.Web.HttpResponse::_context
0x203a7  callvirt instance class System.Web.IHttpHandler System.Web.HttpContext::get_Handler()
0x203ac  isinst   System.Web.UI.Page
0x203b1  stloc.0
0x203b2  ldloc.0
0x203b3  brfalse.s loc_203CD
0x203b5  ldloc.0
0x203b6  callvirt instance bool System.Web.UI.Page::get_IsCallback()
0x203bb  brfalse.s loc_203CD
0x203bd  ldstr    aRedirectNotAll// "Redirect_not_allowed_in_callback"
0x203c2  call     string System.Web.SR::GetString(string name)
0x203c7  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0x203cc  throw
0x203cd  ldarg.0
0x203ce  ldarg.1
0x203cf  call     instance string System.Web.HttpResponse::ApplyRedirectQueryStringIfRequired(string url)
0x203d4  starg.s  1
0x203d6  ldarg.0
0x203d7  ldarg.1
0x203d8  call     instance string System.Web.HttpResponse::ApplyAppPathModifier(string virtualPath)
0x203dd  starg.s  1
0x203df  ldarg.0
0x203e0  ldarg.1
0x203e1  call     instance string System.Web.HttpResponse::ConvertToFullyQualifiedRedirectUrlIfRequired(string url)
0x203e6  starg.s  1
0x203e8  ldarg.0
0x203e9  ldarg.1
0x203ea  call     instance string System.Web.HttpResponse::UrlEncodeRedirect(string url)
0x203ef  starg.s  1
0x203f1  ldarg.0
0x203f2  call     instance void System.Web.HttpResponse::Clear()
0x203f7  ldloc.0
0x203f8  brfalse.s loc_20455
0x203fa  ldloc.0
0x203fb  callvirt instance bool System.Web.UI.Page::get_IsPostBack()
0x20400  brfalse.s loc_20455
0x20402  ldloc.0
0x20403  callvirt instance bool System.Web.UI.Page::get_SmartNavigation()
0x20408  brfalse.s loc_20455
0x2040a  ldarg.0
0x2040b  call     instance class System.Web.HttpRequest System.Web.HttpResponse::get_Request()
0x20410  ldstr    aSmartnavpostba// "__smartNavPostBack"
0x20415  callvirt instance string System.Web.HttpRequest::get_Item(string key)
0x2041a  ldstr    aTrue// "true"
0x2041f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20424  brfalse.s loc_20455
0x20426  ldarg.0
0x20427  ldstr    aBodyAspSmartna// "<BODY><ASP_SMARTNAV_RDIR url=\""
0x2042c  call     instance void System.Web.HttpResponse::Write(string s)
0x20431  ldarg.0
0x20432  ldarg.1
0x20433  call     string System.Web.HttpUtility::HtmlEncode(string s)
0x20438  call     instance void System.Web.HttpResponse::Write(string s)
0x2043d  ldarg.0
0x2043e  ldstr    aAspSmartnavRdi// "\"></ASP_SMARTNAV_RDIR>"
0x20443  call     instance void System.Web.HttpResponse::Write(string s)
0x20448  ldarg.0
0x20449  ldstr    aBody_0// "</BODY>"
0x2044e  call     instance void System.Web.HttpResponse::Write(string s)
0x20453  br.s     loc_204CE
0x20455  call     bool System.Web.HttpRuntime::get_UseIntegratedPipeline()
0x2045a  brfalse.s loc_20467
0x2045c  ldarg.0
0x2045d  ldstr    aTextHtml// "text/html"
0x20462  call     instance void System.Web.HttpResponse::set_ContentType(string value)
0x20467  ldarg.0
0x20468  ldarg.3
0x20469  brtrue.s loc_20472
0x2046b  ldc.i4   0x12E
0x20470  br.s     loc_20477
0x20472  ldc.i4   0x12D
0x20477  call     instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x2047c  ldarg.0
0x2047d  ldarg.1
0x2047e  call     instance void System.Web.HttpResponse::set_RedirectLocation(string value)
0x20483  ldarg.1
0x20484  call     bool System.Web.Util.UriUtil::IsSafeScheme(string url)
0x20489  brfalse.s loc_20495
0x2048b  ldarg.1
0x2048c  call     string System.Web.HttpUtility::HtmlAttributeEncode(string s)
0x20491  starg.s  1
0x20493  br.s     loc_204A2
0x20495  ldarg.1
0x20496  call     string System.Web.HttpUtility::UrlEncode(string str)
0x2049b  call     string System.Web.HttpUtility::HtmlAttributeEncode(string s)
0x204a0  starg.s  1
0x204a2  ldarg.0
0x204a3  ldstr    aHtmlHeadTitleO// "<html><head><title>Object moved</title>"...
0x204a8  call     instance void System.Web.HttpResponse::Write(string s)
0x204ad  ldarg.0
0x204ae  ldstr    aH2ObjectMovedT// "<h2>Object moved to <a href=\""
0x204b3  ldarg.1
0x204b4  ldstr    aHereAH2// "\">here</a>.</h2>\r\n"
0x204b9  call     string [mscorlib]System.String::Concat(string, string, string)
0x204be  call     instance void System.Web.HttpResponse::Write(string s)
0x204c3  ldarg.0
0x204c4  ldstr    aBodyHtml// "</body></html>\r\n"
0x204c9  call     instance void System.Web.HttpResponse::Write(string s)
0x204ce  ldarg.0
0x204cf  ldc.i4.1
0x204d0  stfld    bool System.Web.HttpResponse::_isRequestBeingRedirected
0x204d5  ldsfld   class [mscorlib]System.EventHandler System.Web.HttpResponse::Redirecting
0x204da  stloc.1
0x204db  ldloc.1
0x204dc  brfalse.s loc_204EA
0x204de  ldloc.1
0x204df  ldarg.0
0x204e0  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0x204e5  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x204ea  ldarg.2
0x204eb  brfalse.s loc_204F3
0x204ed  ldarg.0
0x204ee  call     instance void System.Web.HttpResponse::End()
0x204f3  ret
```
