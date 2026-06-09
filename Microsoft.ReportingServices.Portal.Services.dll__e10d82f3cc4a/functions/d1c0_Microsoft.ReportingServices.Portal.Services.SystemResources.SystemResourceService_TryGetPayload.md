# Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::TryGetPayload

- ea: `0xd1c0`
- end: `0xd334`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::TryGetPayload`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x9e80`
- `0xc820`
- `0xc860`
- `0xc910`
- `0xc930`
- `0xcb60`
- `0xd1c0`
- `0xd380`

## pseudocode

```c

```

## disassembly

```asm
0xd1c0  ldarg.2
0xd1c1  brtrue.s loc_D1CE
0xd1c3  ldstr    aTypename// "typeName"
0xd1c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd1cd  throw
0xd1ce  ldarg.s  6
0xd1d0  ldnull
0xd1d1  stind.ref
0xd1d2  ldarg.s  4
0xd1d4  ldnull
0xd1d5  stind.ref
0xd1d6  ldarg.s  5
0xd1d8  ldnull
0xd1d9  stind.ref
0xd1da  ldarg.0
0xd1db  ldarg.1
0xd1dc  ldarg.2
0xd1dd  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::InternalGetSystemResourceByTypeName(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string typeName)
0xd1e2  stloc.0
0xd1e3  ldloc.0
0xd1e4  brtrue.s loc_D1E8
0xd1e6  ldc.i4.0
0xd1e7  ret
0xd1e8  ldarg.3
0xd1e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd1ee  stloc.1
0xd1ef  ldloc.1
0xd1f0  brtrue.s loc_D25A
0xd1f2  ldloc.0
0xd1f3  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xd1f8  ldarg.3
0xd1f9  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xd1fe  brtrue.s loc_D244
0xd200  ldarg.1
0xd201  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0xd206  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SystemResourceManager()
0xd20b  stloc.2
0xd20c  ldc.i4.2
0xd20d  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourceManager
0xd212  dup
0xd213  ldc.i4.0
0xd214  ldloc.2
0xd215  stelem.ref
0xd216  dup
0xd217  ldc.i4.1
0xd218  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_embeddedResources
0xd21d  stelem.ref
0xd21e  stloc.3
0xd21f  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_processingManager
0xd224  ldloc.0
0xd225  ldloc.3
0xd226  callvirt instance void Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager::ProcessResource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource resource, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourceManager> resourceManagers)
0xd22b  leave.s  loc_D244
0xd22d  stloc.s  4
0xd22f  ldarg.0
0xd230  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_logger
0xd235  ldc.i4.1
0xd236  ldloc.s  4
0xd238  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd23d  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd242  leave.s  loc_D244
0xd244  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_processingManager
0xd249  ldloc.0
0xd24a  ldarg.3
0xd24b  ldarg.s  6
0xd24d  ldarg.s  4
0xd24f  ldarg.s  5
0xd251  callvirt instance bool Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceProcessingManager::TryLoadItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource resource, string itemName, [out] unsigned int8[]& bytes, [out] string& contentType, [out] string& fileName)
0xd256  brfalse.s loc_D25A
0xd258  ldc.i4.1
0xd259  ret
0xd25a  ldloc.0
0xd25b  isinst   Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource
0xd260  brfalse.s loc_D2B4
0xd262  ldsfld   class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_embeddedResources
0xd267  ldarg.2
0xd268  ldarg.3
0xd269  ldarg.s  6
0xd26b  callvirt instance bool Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::TryLoadContentItem(string typeName, string key, [out] unsigned int8[]& bytes)
0xd270  brfalse.s loc_D2B2
0xd272  ldloc.1
0xd273  brfalse.s loc_D290
0xd275  ldarg.s  4
0xd277  ldstr    aApplicationOct// "application/octet-stream"
0xd27c  stind.ref
0xd27d  ldarg.s  5
0xd27f  ldloc.0
0xd280  isinst   Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource
0xd285  callvirt instance string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource::get_PackageName()
0xd28a  stind.ref
0xd28b  br       loc_D332
0xd290  ldarg.s  4
0xd292  ldloc.0
0xd293  isinst   Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource
0xd298  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource::get_Contents()
0xd29d  ldarg.3
0xd29e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Item(void)
0xd2a3  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::get_ContentType()
0xd2a8  stind.ref
0xd2a9  ldarg.s  5
0xd2ab  ldarg.3
0xd2ac  stind.ref
0xd2ad  br       loc_D332
0xd2b2  ldc.i4.0
0xd2b3  ret
0xd2b4  ldloc.1
0xd2b5  brfalse.s loc_D2C1
0xd2b7  ldloc.0
0xd2b8  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_PackageId()
0xd2bd  stloc.s  5
0xd2bf  br.s     loc_D2F5
0xd2c1  ldloc.0
0xd2c2  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xd2c7  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Keys()
0xd2cc  ldarg.3
0xd2cd  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xd2d2  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0xd2d7  brfalse.s loc_D2F3
0xd2d9  ldloc.0
0xd2da  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xd2df  ldarg.3
0xd2e0  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0xd2e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0xd2ea  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0xd2ef  stloc.s  5
0xd2f1  br.s     loc_D2F5
0xd2f3  ldc.i4.0
0xd2f4  ret
0xd2f5  ldarg.0
0xd2f6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::_catalogRepository
0xd2fb  ldarg.1
0xd2fc  ldloc.s  5
0xd2fe  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContent(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xd303  stloc.s  6
0xd305  ldloc.s  6
0xd307  brfalse.s loc_D314
0xd309  ldloc.s  6
0xd30b  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xd310  brtrue.s loc_D314
0xd312  ldc.i4.0
0xd313  ret
0xd314  ldarg.s  6
0xd316  ldloc.s  6
0xd318  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xd31d  stind.ref
0xd31e  ldarg.s  4
0xd320  ldloc.s  6
0xd322  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0xd327  stind.ref
0xd328  ldarg.s  5
0xd32a  ldloc.s  6
0xd32c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0xd331  stind.ref
0xd332  ldc.i4.1
0xd333  ret
```
