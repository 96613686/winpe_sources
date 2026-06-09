# <>c__DisplayClass86_0::<UpdateExcel>b__0

- ea: `0x1da30`
- end: `0x1db1f`
- name: `<>c__DisplayClass86_0::<UpdateExcel>b__0`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x3ed0`
- `0x3f30`
- `0x108c0`
- `0x1da30`

## string_xrefs

- `0x1da40`: `UpdateExcel`

## pseudocode

```c

```

## disassembly

```asm
0x1da30  ldc.i4.2
0x1da31  newarr   [mscorlib]System.String
0x1da36  dup
0x1da37  ldc.i4.0
0x1da38  ldstr    aSql// "SQL"
0x1da3d  stelem.ref
0x1da3e  dup
0x1da3f  ldc.i4.1
0x1da40  ldstr    aUpdateexcel// "UpdateExcel"
0x1da45  stelem.ref
0x1da46  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x1da4b  stloc.0
0x1da4c  ldarg.0
0x1da4d  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x1da52  ldarg.0
0x1da53  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1da58  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1da5d  ldarg.0
0x1da5e  ldfld    string <>c__DisplayClass86_0::origItemPath
0x1da63  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::ThrowIfExcelFileExtensionChanged(string, string)
0x1da68  ldarg.0
0x1da69  ldfld    bool <>c__DisplayClass86_0::updateProperties
0x1da6e  brfalse.s loc_1DA8E
0x1da70  ldarg.0
0x1da71  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass86_0::<>4__this
0x1da76  ldarg.0
0x1da77  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x1da7c  ldarg.0
0x1da7d  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1da82  ldarg.0
0x1da83  ldfld    string <>c__DisplayClass86_0::origItemPath
0x1da88  ldnull
0x1da89  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateItemProperties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, string itemPath, [opt] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[] additionalProperties)
0x1da8e  ldarg.0
0x1da8f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1da94  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0x1da99  brfalse.s loc_1DAE8
0x1da9b  ldarg.0
0x1da9c  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x1daa1  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetExcelWorkbookContentsAction()
0x1daa6  dup
0x1daa7  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsActionParameters>::get_ActionParameters()
0x1daac  ldarg.0
0x1daad  ldfld    string <>c__DisplayClass86_0::origItemPath
0x1dab2  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemActionParameters::set_ItemPath(string)
0x1dab7  dup
0x1dab8  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsActionParameters>::get_ActionParameters()
0x1dabd  ldarg.0
0x1dabe  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1dac3  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent Microsoft.ReportingServices.Portal.Services.Extensions.CatalogItemExtensions::ToCatalogItemStreamContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x1dac8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemContentActionParameters::set_CatalogItemContent(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent)
0x1dacd  dup
0x1dace  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsActionParameters>::get_ActionParameters()
0x1dad3  ldarg.0
0x1dad4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1dad9  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x1dade  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsActionParameters::set_MimeType(string)
0x1dae3  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExcelWorkbookContentsActionParameters>::PerformActionNow()
0x1dae8  ldarg.0
0x1dae9  ldfld    bool <>c__DisplayClass86_0::renameOrMove
0x1daee  brfalse.s loc_1DB12
0x1daf0  ldarg.0
0x1daf1  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass86_0::<>4__this
0x1daf6  ldarg.0
0x1daf7  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass86_0::rsService
0x1dafc  ldarg.0
0x1dafd  ldfld    string <>c__DisplayClass86_0::origItemPath
0x1db02  ldarg.0
0x1db03  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook <>c__DisplayClass86_0::item
0x1db08  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1db0d  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::RenameOrMoveItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string sourcePath, string destPath)
0x1db12  leave.s  loc_1DB1E
0x1db14  ldloc.0
0x1db15  brfalse.s loc_1DB1D
0x1db17  ldloc.0
0x1db18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1db1d  endfinally
0x1db1e  ret
```
