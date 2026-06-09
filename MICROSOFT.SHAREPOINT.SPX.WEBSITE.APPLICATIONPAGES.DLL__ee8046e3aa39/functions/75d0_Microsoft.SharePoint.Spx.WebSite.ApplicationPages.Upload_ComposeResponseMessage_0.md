# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::ComposeResponseMessage_0

- ea: `0x75d0`
- end: `0x7665`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::ComposeResponseMessage_0`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x75c0`
- `0x7670`

## callees

- `0x75d0`

## pseudocode

```c

```

## disassembly

```asm
0x75d0  ldarg.0
0x75d1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75d6  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x75db  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x75e0  ldstr    aIe// "IE"
0x75e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x75ea  brtrue.s loc_75F3
0x75ec  ldsfld   string [mscorlib]System.String::Empty
0x75f1  br.s     loc_75F8
0x75f3  ldstr    aParent// "parent."
0x75f8  stloc.0
0x75f9  ldarg.2
0x75fa  ldc.i4.0
0x75fb  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x7600  stloc.1
0x7601  ldarg.3
0x7602  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7607  brfalse.s loc_761C
0x7609  ldarg.0
0x760a  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.Upload::optimizeImage
0x760f  brtrue.s loc_7614
0x7611  ldarg.2
0x7612  br.s     loc_761A
0x7614  ldarg.2
0x7615  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.FileManager::GetConvertedImageFileName(string)
0x761a  starg.s  3
0x761c  ldarg.3
0x761d  ldc.i4.0
0x761e  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::JavaScriptEncode(string, bool)
0x7623  stloc.2
0x7624  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7629  stloc.3
0x762a  ldloc.3
0x762b  ldstr    aScriptTypeText_1// "<script type='text/javascript'>{0}paren"...
0x7630  ldc.i4.4
0x7631  newarr   [mscorlib]System.Object
0x7636  stloc.s  4
0x7638  ldloc.s  4
0x763a  ldc.i4.0
0x763b  ldloc.0
0x763c  stelem.ref
0x763d  ldloc.s  4
0x763f  ldc.i4.1
0x7640  ldarg.1
0x7641  box      FileUploadStatus
0x7646  callvirt instance string [mscorlib]System.Object::ToString()
0x764b  stelem.ref
0x764c  ldloc.s  4
0x764e  ldc.i4.2
0x764f  ldloc.1
0x7650  stelem.ref
0x7651  ldloc.s  4
0x7653  ldc.i4.3
0x7654  ldloc.2
0x7655  stelem.ref
0x7656  ldloc.s  4
0x7658  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object[])
0x765d  pop
0x765e  ldloc.3
0x765f  callvirt instance string [mscorlib]System.Object::ToString()
0x7664  ret
```
