# Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::.cctor

- ea: `0x3fd30`
- end: `0x3fdd1`
- name: `Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::.cctor`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x3fd30`: `https://marketplace.visualstudio.com`
- `0x3fd70`: `extensionquery`
- `0x3fdc6`: `/Microsoft.VisualStudio.Ide.Payload?redirect=true&install=true`

## pseudocode

```c

```

## disassembly

```asm
0x3fd30  ldstr    aHttpsMarketpla// "https://marketplace.visualstudio.com"
0x3fd35  stsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VisualStudioMarketplaceBaseUri
0x3fd3a  ldsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VisualStudioMarketplaceBaseUri
0x3fd3f  ldstr    aItemsItemname// "/items?itemName="
0x3fd44  call     string [mscorlib]System.String::Concat(string, string)
0x3fd49  stsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VisualStudioMarketplaceItemPagePrefix
0x3fd4e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation>::.ctor()
0x3fd53  dup
0x3fd54  newobj   instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::.ctor()
0x3fd59  dup
0x3fd5a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.VisualStudio.Services.Gallery.WebApi]Microsoft.VisualStudio.Services.Gallery.GalleryResourceIds::ExtensionQueryLocationId
0x3fd5f  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_Id(valuetype [mscorlib]System.Guid)
0x3fd64  dup
0x3fd65  ldstr    aGallery// "gallery"
0x3fd6a  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_Area(string)
0x3fd6f  dup
0x3fd70  ldstr    aExtensionquery_0// "extensionquery"
0x3fd75  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_ResourceName(string)
0x3fd7a  dup
0x3fd7b  ldstr    aApisPublicArea// "_apis/public/{area}/{resource}"
0x3fd80  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_RouteTemplate(string)
0x3fd85  dup
0x3fd86  ldc.i4.1
0x3fd87  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_ResourceVersion(int32)
0x3fd8c  dup
0x3fd8d  ldstr    a20// "2.0"
0x3fd92  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x3fd97  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_MinVersion(class [mscorlib]System.Version)
0x3fd9c  dup
0x3fd9d  ldstr    a70// "7.0"
0x3fda2  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x3fda7  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_MaxVersion(class [mscorlib]System.Version)
0x3fdac  dup
0x3fdad  ldstr    a00// "0.0"
0x3fdb2  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x3fdb7  callvirt instance void [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation::set_ReleasedVersion(class [mscorlib]System.Version)
0x3fdbc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation>::Add(var<u1>)
0x3fdc1  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Services.WebApi]Microsoft.VisualStudio.Services.WebApi.ApiResourceLocation> Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::ResourceLocations
0x3fdc6  ldstr    aMicrosoftVisua_61// "/Microsoft.VisualStudio.Ide.Payload?red"...
0x3fdcb  stsfld   string Microsoft.VisualStudio.Setup.Services.MarketplaceExtensionService::VSUriPostfix
0x3fdd0  ret
```
