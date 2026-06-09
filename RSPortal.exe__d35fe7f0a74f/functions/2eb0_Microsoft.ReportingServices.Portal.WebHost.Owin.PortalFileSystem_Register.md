# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::Register

- ea: `0x2eb0`
- end: `0x2f10`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::Register`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x2eb0`
- `0x2f10`
- `0x2fc0`
- `0x2fd0`
- `0x2fe0`

## string_xrefs

- `0x2ef3`: `Unable to configure local file server`

## pseudocode

```c

```

## disassembly

```asm
0x2eb0  ldarg.2
0x2eb1  ldc.i4.4
0x2eb2  ldstr    aUsingPortalv2// "Using PortalV2: "
0x2eb7  ldc.i4.1
0x2eb8  stloc.0
0x2eb9  ldloca.s 0
0x2ebb  call     instance string [mscorlib]System.Boolean::ToString()
0x2ec0  call     string [mscorlib]System.String::Concat(string, string)
0x2ec5  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2eca  ldarg.1
0x2ecb  callvirt instance bool [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IExposureControl::get_DogfoodEnabled()
0x2ed0  brfalse.s loc_2EFE
0x2ed2  call     string Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::get_WebRootDir()
0x2ed7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2edc  brtrue.s loc_2EFE
0x2ede  ldarg.0
0x2edf  call     class [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.IFileSystem Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootFileSystem()
0x2ee4  call     class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetFileServerOptions(class [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.IFileSystem webRootFS)
0x2ee9  call     class [Owin]Owin.IAppBuilder [Microsoft.Owin.StaticFiles]Owin.FileServerExtensions::UseFileServer(class [Owin]Owin.IAppBuilder, class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions)
0x2eee  pop
0x2eef  leave.s  loc_2F0F
0x2ef1  ldarg.2
0x2ef2  ldc.i4.1
0x2ef3  ldstr    aUnableToConfig// "Unable to configure local file server"
0x2ef8  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2efd  throw
0x2efe  ldarg.0
0x2eff  call     class [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.IFileSystem Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetWebRootInMemoryFileSystem()
0x2f04  call     class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::GetFileServerOptions(class [Microsoft.Owin.FileSystems]Microsoft.Owin.FileSystems.IFileSystem webRootFS)
0x2f09  call     class [Owin]Owin.IAppBuilder [Microsoft.Owin.StaticFiles]Owin.FileServerExtensions::UseFileServer(class [Owin]Owin.IAppBuilder, class [Microsoft.Owin.StaticFiles]Microsoft.Owin.StaticFiles.FileServerOptions)
0x2f0e  pop
0x2f0f  ret
```
