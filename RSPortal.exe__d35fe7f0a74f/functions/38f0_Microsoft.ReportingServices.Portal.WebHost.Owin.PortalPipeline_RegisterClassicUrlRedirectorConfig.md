# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalPipeline::RegisterClassicUrlRedirectorConfig

- ea: `0x38f0`
- end: `0x3945`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalPipeline::RegisterClassicUrlRedirectorConfig`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x1ba0`
- `0x33c0`
- `0x33e0`

## pseudocode

```c

```

## disassembly

```asm
0x38f0  ldarg.0
0x38f1  ldarg.1
0x38f2  ldstr    aPagesReportAsp// "/Pages/Report.aspx"
0x38f7  ldstr    aReport// "/report"
0x38fc  ldc.i4.1
0x38fd  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, string basePath, string newBasePath, bool appendItemPath)
0x3902  ldarg.0
0x3903  ldarg.1
0x3904  ldstr    aPagesFolderAsp// "/Pages/Folder.aspx"
0x3909  ldstr    aBrowse// "/browse"
0x390e  ldc.i4.1
0x390f  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, string basePath, string newBasePath, bool appendItemPath)
0x3914  ldarg.0
0x3915  ldarg.1
0x3916  ldstr    aPagesUsersetti// "/Pages/UserSettings.aspx"
0x391b  ldstr    aSettings// "/settings"
0x3920  ldc.i4.0
0x3921  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, string basePath, string newBasePath, bool appendItemPath)
0x3926  ldarg.0
0x3927  ldarg.1
0x3928  ldstr    aPagesSubscript// "/Pages/Subscriptions.aspx"
0x392d  ldstr    aSubscriptions// "/subscriptions"
0x3932  ldc.i4.0
0x3933  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, string basePath, string newBasePath, bool appendItemPath)
0x3938  ldarg.0
0x3939  ldarg.1
0x393a  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.AsmxRedirecterRule::.ctor(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration)
0x393f  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.UrlRedirecterMiddleware::Register(class [Owin]Owin.IAppBuilder app, class Microsoft.ReportingServices.Portal.WebHost.Owin.IUrlRedirecterRule rule)
0x3944  ret
```
