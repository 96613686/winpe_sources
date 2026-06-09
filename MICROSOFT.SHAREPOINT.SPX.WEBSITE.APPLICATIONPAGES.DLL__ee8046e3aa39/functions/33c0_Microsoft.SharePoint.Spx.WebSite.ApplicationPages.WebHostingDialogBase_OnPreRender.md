# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::OnPreRender

- ea: `0x33c0`
- end: `0x33f9`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::OnPreRender`
- size: `57`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3890`
- `0x4770`
- `0x4b30`
- `0x13190`

## string_xrefs

- `0x33cd`: `no-cache`
- `0x33e2`: `no-cache`

## pseudocode

```c

```

## disassembly

```asm
0x33c0  ldarg.0
0x33c1  ldarg.1
0x33c2  call     instance void [System.Web]System.Web.UI.Control::OnPreRender(class [mscorlib]System.EventArgs)
0x33c7  ldarg.0
0x33c8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x33cd  ldstr    aNoCache// "no-cache"
0x33d2  callvirt instance void [System.Web]System.Web.HttpResponse::set_CacheControl(string)
0x33d7  ldarg.0
0x33d8  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x33dd  ldstr    aPragma// "Pragma"
0x33e2  ldstr    aNoCache// "no-cache"
0x33e7  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x33ec  ldarg.0
0x33ed  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x33f2  ldc.i4.m1
0x33f3  callvirt instance void [System.Web]System.Web.HttpResponse::set_Expires(int32)
0x33f8  ret
```
