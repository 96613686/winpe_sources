# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::.cctor

- ea: `0x4490`
- end: `0x44b9`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::.cctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x44a4`: `<script>commitWindow('{0}');</script>`

## pseudocode

```c

```

## disassembly

```asm
0x4490  ldstr    aScriptAlert0Sc// "<script>alert(\"{0}\");</script>"
0x4495  stsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScript
0x449a  ldstr    a068529c38aaa45// "068529C3-8AAA-45b3-89DA-6030BD04E39C"
0x449f  stsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileExistsMessageScriptGuid
0x44a4  ldstr    aScriptCommitwi// "<script>commitWindow('{0}');</script>"
0x44a9  stsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileCreationSuccessScript
0x44ae  ldstr    aCb36f4a3Bb0c46// "CB36F4A3-BB0C-4602-9514-E01DC8214834"
0x44b3  stsfld   string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CreatePage::fileCreationSuccessScriptGuid
0x44b8  ret
```
