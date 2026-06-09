# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetPageContent

- ea: `0x1bf0`
- end: `0x1c2a`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetPageContent`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb50`

## callees

- `0x1bf0`
- `0x24d0`

## string_xrefs

- `0x1c24`: `DeletedFile`

## pseudocode

```c

```

## disassembly

```asm
0x1bf0  ldstr    aSitedesignerSi_2// "SiteDesigner_SiteIOGetPageContent"
0x1bf5  ldnull
0x1bf6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x1bfb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x1c00  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x1c05  stloc.0
0x1c06  ldloc.0
0x1c07  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x1c0c  stloc.1
0x1c0d  ldloc.1
0x1c0e  ldarg.0
0x1c0f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x1c14  stloc.2
0x1c15  ldloc.2
0x1c16  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_Exists()
0x1c1b  brfalse.s loc_1C24
0x1c1d  ldloc.2
0x1c1e  call     string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.SiteIO::GetPageContent(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile file)
0x1c23  ret
0x1c24  ldstr    aDeletedfile// "DeletedFile"
0x1c29  ret
```
