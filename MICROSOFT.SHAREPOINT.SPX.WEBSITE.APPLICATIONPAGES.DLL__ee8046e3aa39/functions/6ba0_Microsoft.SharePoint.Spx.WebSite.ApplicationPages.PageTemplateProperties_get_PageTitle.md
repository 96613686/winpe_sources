# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_PageTitle

- ea: `0x6ba0`
- end: `0x6bc4`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::get_PageTitle`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6ba0`

## string_xrefs

- `0x6ba8`: `PageTemplates_SaveTitleHeader`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.0
0x6ba1  ldfld    bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::isSaveMode
0x6ba6  brfalse.s loc_6BB3
0x6ba8  ldstr    aPagetemplatesS// "PageTemplates_SaveTitleHeader"
0x6bad  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x6bb2  ret
0x6bb3  ldarg.0
0x6bb4  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageTemplateProperties::spFile
0x6bb9  ldstr    aVtiTitle// "vti_title"
0x6bbe  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.PageManager::GetPagePropertyValue(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile, string)
0x6bc3  ret
```
