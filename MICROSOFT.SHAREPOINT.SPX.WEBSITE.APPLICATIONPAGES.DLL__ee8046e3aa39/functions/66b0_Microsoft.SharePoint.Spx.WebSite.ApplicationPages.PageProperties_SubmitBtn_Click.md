# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageProperties::SubmitBtn_Click

- ea: `0x66b0`
- end: `0x66d5`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageProperties::SubmitBtn_Click`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x66e0`

## string_xrefs

- `0x66c9`: `commitWindow();`

## pseudocode

```c

```

## disassembly

```asm
0x66b0  ldarg.0
0x66b1  ldarg.1
0x66b2  ldarg.2
0x66b3  call     instance void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageProperties::ApplyBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x66b8  ldarg.0
0x66b9  call     instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x66be  ldarg.0
0x66bf  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x66c4  ldstr    aClosewindow// "closeWindow"
0x66c9  ldstr    aCommitwindow// "commitWindow();"
0x66ce  ldc.i4.1
0x66cf  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string, bool)
0x66d4  ret
```
