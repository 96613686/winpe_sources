# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetFileServerOptions

- ea: `0x2f10`
- end: `0x2f8c`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetFileServerOptions`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2eb0`

## callees

- `0x2f10`
- `0x2f90`

## string_xrefs

- `0x2f6c`: `.json`
- `0x2f71`: `application/json`
- `0x2f7c`: `.resjson`
- `0x2f81`: `application/json; charset=UTF-8`

## pseudocode

```c

```

## disassembly

```asm
0x2f10  newobj   instance void [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions::.ctor()
0x2f15  dup
0x2f16  ldsfld   valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.PathString::Empty
0x2f1b  callvirt instance void class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.Infrastructure.SharedOptionsBase`1<class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions>::set_RequestPath(valuetype [Microsoft.Owin]Microsoft.Owin.PathString)
0x2f20  dup
0x2f21  ldarg.0
0x2f22  callvirt instance void class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.Infrastructure.SharedOptionsBase`1<class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions>::set_FileSystem(class [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.IFileSystem)
0x2f27  dup
0x2f28  callvirt instance class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.StaticFileOptions [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions::get_StaticFileOptions()
0x2f2d  callvirt instance class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.IContentTypeProvider [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.StaticFileOptions::get_ContentTypeProvider()
0x2f32  isinst   [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider
0x2f37  stloc.0
0x2f38  ldloc.0
0x2f39  brfalse.s loc_2F8B
0x2f3b  ldloc.0
0x2f3c  ldstr    aCss// ".css"
0x2f41  ldstr    aTextCssCharset// "text/css; charset=UTF-8"
0x2f46  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings(class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider provider, string key, string value)
0x2f4b  ldloc.0
0x2f4c  ldstr    aHtml// ".html"
0x2f51  ldstr    aTextHtmlCharse// "text/html; charset=UTF-8"
0x2f56  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings(class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider provider, string key, string value)
0x2f5b  ldloc.0
0x2f5c  ldstr    aJs// ".js"
0x2f61  ldstr    aApplicationJav// "application/javascript; charset=UTF-8"
0x2f66  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings(class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider provider, string key, string value)
0x2f6b  ldloc.0
0x2f6c  ldstr    aJson// ".json"
0x2f71  ldstr    aApplicationJso// "application/json"
0x2f76  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings(class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider provider, string key, string value)
0x2f7b  ldloc.0
0x2f7c  ldstr    aResjson// ".resjson"
0x2f81  ldstr    aApplicationJso_0// "application/json; charset=UTF-8"
0x2f86  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::UpdateContentProviderMappings(class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.ContentTypes.FileExtensionContentTypeProvider provider, string key, string value)
0x2f8b  ret
```
