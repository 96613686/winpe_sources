# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ResetPublicSiteDialog::RedirectToAccessDeniedPage

- ea: `0x7210`
- end: `0x723c`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ResetPublicSiteDialog::RedirectToAccessDeniedPage`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x71a0`

## callees

- `0x7210`

## string_xrefs

- `0x7223`: `/AccessDenied.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x7210  ldarg.0
0x7211  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7216  brtrue.s loc_723B
0x7218  ldarg.0
0x7219  ldstr    asc_20240// "/"
0x721e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::get_ContextLayoutsFolder()
0x7223  ldstr    aAccessdeniedAs// "/AccessDenied.aspx"
0x7228  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x722d  stloc.0
0x722e  ldloc.0
0x722f  ldc.i4.1
0x7230  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7235  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::Redirect(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPRedirectFlags, class [System.Web]System.Web.HttpContext)
0x723a  pop
0x723b  ret
```
