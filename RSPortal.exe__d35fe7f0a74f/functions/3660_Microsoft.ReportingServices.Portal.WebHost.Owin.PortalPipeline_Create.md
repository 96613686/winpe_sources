# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalPipeline::Create

- ea: `0x3660`
- end: `0x38e1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalPipeline::Create`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b80`

## callees

- `0xbf0`
- `0x11b0`
- `0x15a0`
- `0x1600`
- `0x1800`
- `0x2420`
- `0x26f0`
- `0x2af0`
- `0x2eb0`
- `0x3020`
- `0x3120`
- `0x38f0`

## pseudocode

```c

```

## disassembly

```asm
0x3660  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x3665  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x366a  ldarg.1
0x366b  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.PropertyProvider::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigManager)
0x3670  ldc.i4.0
0x3671  newobj   instance void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.AuthExtensionProvider::.ctor(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration, class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.IPropertyProvider, bool)
0x3676  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x367b  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x3680  newobj   instance void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.AuthenticationService::.ctor(class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IAuthExtensionProvider, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration)
0x3685  stloc.0
0x3686  newobj   instance void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.ExposureControl::.ctor()
0x368b  stloc.1
0x368c  ldarg.1
0x368d  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Configuration.OAuthClientConfigurationService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x3692  stloc.2
0x3693  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Configuration.EncryptionService::.ctor()
0x3698  stloc.3
0x3699  ldloc.3
0x369a  ldarg.2
0x369b  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CsrfTokenValidation::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService encryptionService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x36a0  pop
0x36a1  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.DatabaseService::.ctor()
0x36a6  stloc.s  4
0x36a8  ldarg.1
0x36a9  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRS2010Proxy::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x36ae  stloc.s  5
0x36b0  ldloc.s  5
0x36b2  ldarg.2
0x36b3  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Repositories.SystemService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x36b8  stloc.s  6
0x36ba  ldloc.s  5
0x36bc  ldloc.s  6
0x36be  ldarg.2
0x36bf  ldarg.1
0x36c0  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x36c5  stloc.s  7
0x36c7  ldloc.s  5
0x36c9  ldloc.s  7
0x36cb  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository)
0x36d0  stloc.s  8
0x36d2  ldarg.1
0x36d3  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SoapProxy.SoapRsExecutionProxyFactory::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager)
0x36d8  stloc.s  9
0x36da  ldloc.s  5
0x36dc  ldloc.s  9
0x36de  ldarg.2
0x36df  ldloc.s  7
0x36e1  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.DataService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRSExecutionProxyFactory, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository)
0x36e6  stloc.s  0xA
0x36e8  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.UserInfoService::.ctor()
0x36ed  stloc.s  0xB
0x36ef  ldarg.2
0x36f0  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.PowerBIIntegrationService::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x36f5  stloc.s  0xC
0x36f7  ldloc.s  0xC
0x36f9  ldloc.s  8
0x36fb  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.NotificationService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService)
0x3700  stloc.s  0xD
0x3702  ldloc.s  7
0x3704  ldarg.2
0x3705  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x370a  stloc.s  0xE
0x370c  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Services.TelemetryConfigurationFactory::.ctor()
0x3711  ldarg.1
0x3712  ldloc.s  6
0x3714  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.TelemetryService::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryConfigurationFactory, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService)
0x3719  stloc.s  0xF
0x371b  newobj   instance void [Microsoft.Owin.Cors]Microsoft.Owin.Cors.CorsOptions::.ctor()
0x3720  stloc.s  0x10
0x3722  ldloc.s  0x10
0x3724  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsPolicyProvider::.ctor()
0x3729  callvirt instance void [Microsoft.Owin.Cors]Microsoft.Owin.Cors.CorsOptions::set_PolicyProvider(class [Microsoft.Owin.Cors]Microsoft.Owin.Cors.ICorsPolicyProvider)
0x372e  ldarg.0
0x372f  ldc.i4.2
0x3730  newarr   [mscorlib]System.Object
0x3735  dup
0x3736  ldc.i4.0
0x3737  ldloc.s  0x10
0x3739  stelem.ref
0x373a  dup
0x373b  ldc.i4.1
0x373c  ldarg.2
0x373d  stelem.ref
0x373e  call     T0x2B000011
0x3743  pop
0x3744  ldloc.s  5
0x3746  ldloc.s  6
0x3748  ldloc.s  7
0x374a  ldloc.s  8
0x374c  ldarg.2
0x374d  ldloc.s  0xA
0x374f  ldloc.3
0x3750  ldarg.1
0x3751  ldloc.s  0xB
0x3753  ldloc.s  0xD
0x3755  ldloc.s  0xC
0x3757  ldloc.s  0xE
0x3759  ldloc.s  0xF
0x375b  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy soapProxy, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService subscriptionService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService dataService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService encryptionService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigurationManager, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService userInfoService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.INotificationService notificationService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService powerBIIntegrationService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService systemResourceService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService telemetryService)
0x3760  stloc.s  0x11
0x3762  ldloc.s  5
0x3764  ldloc.s  6
0x3766  ldloc.s  7
0x3768  ldloc.s  8
0x376a  ldarg.2
0x376b  ldloc.s  0xA
0x376d  ldloc.3
0x376e  ldarg.1
0x376f  ldloc.s  0xB
0x3771  ldloc.s  0xD
0x3773  ldloc.s  0xC
0x3775  ldloc.s  0xE
0x3777  ldloc.s  0xF
0x3779  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x377e  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x3783  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::.ctor(class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy soapProxy, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService subscriptionService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService dataService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService encryptionService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager portalConfigurationManager, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService userInfoService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.INotificationService notificationService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IPowerBIIntegrationService powerBIIntegrationService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService systemResourceService, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService telemetryService, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration)
0x3788  stloc.s  0x12
0x378a  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x378f  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x3794  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootVX::.ctor(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration)
0x3799  stloc.s  0x13
0x379b  newobj   instance void [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.WebApi.StaticAssembliesResolverFactory::.ctor()
0x37a0  stloc.s  0x14
0x37a2  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x37a7  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x37ac  stloc.s  0x15
0x37ae  ldarg.0
0x37af  ldloc.s  0x15
0x37b1  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Middleware.AuthSchemeConfig::Configure(class [Owin]Owin.IAppBuilder, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration)
0x37b6  ldarg.0
0x37b7  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Middleware.HttpsRedirectMiddleware::Register(class [Owin]Owin.IAppBuilder)
0x37bc  ldarg.0
0x37bd  ldc.i4.2
0x37be  newarr   [mscorlib]System.Object
0x37c3  dup
0x37c4  ldc.i4.0
0x37c5  ldarg.2
0x37c6  stelem.ref
0x37c7  dup
0x37c8  ldc.i4.1
0x37c9  ldarg.1
0x37ca  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x37cf  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_LogClientIPAddress()
0x37d4  box      [mscorlib]System.Boolean
0x37d9  stelem.ref
0x37da  call     T0x2B000012
0x37df  pop
0x37e0  ldarg.0
0x37e1  ldloc.s  0x15
0x37e3  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Middleware.BasicAuthenticationMiddleware::Register(class [Owin]Owin.IAppBuilder, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration)
0x37e8  ldarg.0
0x37e9  ldloc.0
0x37ea  ldloc.s  0x15
0x37ec  ldc.i4.1
0x37ed  call     void [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Middleware.CustomAuthenticationMiddleware::Register(class [Owin]Owin.IAppBuilder, class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IAuthenticationService, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration, bool)
0x37f2  ldarg.0
0x37f3  call     T0x2B000001
0x37f8  call     T0x2B000013
0x37fd  pop
0x37fe  ldarg.0
0x37ff  ldloc.s  0x15
0x3801  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalPipeline::RegisterClassicUrlRedirectorConfig(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration)
0x3806  ldarg.0
0x3807  call     T0x2B000001
0x380c  call     T0x2B000014
0x3811  pop
0x3812  ldarg.0
0x3813  call     T0x2B000001
0x3818  call     T0x2B000015
0x381d  pop
0x381e  ldarg.0
0x381f  call     T0x2B000001
0x3824  call     T0x2B000016
0x3829  pop
0x382a  ldarg.0
0x382b  ldc.i4.1
0x382c  newarr   [mscorlib]System.Object
0x3831  dup
0x3832  ldc.i4.0
0x3833  ldloc.s  0x15
0x3835  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerWebAppVirtualDirectory()
0x383a  newobj   instance void Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::.ctor(string virtualRoot)
0x383f  stelem.ref
0x3840  call     T0x2B000017
0x3845  pop
0x3846  ldarg.0
0x3847  call     T0x2B000001
0x384c  call     T0x2B000018
0x3851  pop
0x3852  ldarg.0
0x3853  ldc.i4.2
0x3854  newarr   [mscorlib]System.Object
0x3859  dup
0x385a  ldc.i4.0
0x385b  ldloc.2
0x385c  stelem.ref
0x385d  dup
0x385e  ldc.i4.1
0x385f  ldarg.2
0x3860  stelem.ref
0x3861  call     T0x2B000019
0x3866  pop
0x3867  ldarg.0
0x3868  ldc.i4.3
0x3869  newarr   [mscorlib]System.Object
0x386e  dup
0x386f  ldc.i4.0
0x3870  ldloc.s  0x15
0x3872  stelem.ref
0x3873  dup
0x3874  ldc.i4.1
0x3875  ldloc.1
0x3876  stelem.ref
0x3877  dup
0x3878  ldc.i4.2
0x3879  ldarg.2
0x387a  stelem.ref
0x387b  call     T0x2B00001A
0x3880  pop
0x3881  ldarg.0
0x3882  ldloc.1
0x3883  ldarg.2
0x3884  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalFileSystem::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Owin.Common]Microsoft.BIServer.Owin.Common.Services.IExposureControl exposureControl, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x3889  ldarg.0
0x388a  ldc.i4.3
0x388b  newarr   [mscorlib]System.Object
0x3890  dup
0x3891  ldc.i4.0
0x3892  ldloc.2
0x3893  stelem.ref
0x3894  dup
0x3895  ldc.i4.1
0x3896  ldloc.0
0x3897  stelem.ref
0x3898  dup
0x3899  ldc.i4.2
0x389a  ldarg.2
0x389b  stelem.ref
0x389c  call     T0x2B00001B
0x38a1  pop
0x38a2  ldarg.0
0x38a3  call     T0x2B000001
0x38a8  call     T0x2B00001C
0x38ad  pop
0x38ae  ldarg.0
0x38af  ldloc.s  0x15
0x38b1  ldarg.2
0x38b2  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::Register(class [Owin]Owin.IAppBuilder app, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration serverConfiguration, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x38b7  ldarg.0
0x38b8  ldloc.s  4
0x38ba  ldarg.2
0x38bb  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.DatabaseAvailableMiddleware::RegisterDatabaseAvailableMiddleware(class [Owin]Owin.IAppBuilder app, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDatabaseService databaseService, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger)
0x38c0  ldarg.0
0x38c1  ldloc.s  0x13
0x38c3  ldloc.s  0x14
0x38c5  call     void Microsoft.ReportingServices.Portal.WebHost.Owin.PortalWebApi::Register(class [Owin]Owin.IAppBuilder app, class [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator controllerActivator, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory assembliesResolverFactory)
0x38ca  ldarg.0
0x38cb  ldarg.2
0x38cc  ldloc.s  0x14
0x38ce  ldloc.s  0x11
0x38d0  call     void [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV1(class [Owin]Owin.IAppBuilder, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory, class [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator)
0x38d5  ldarg.0
0x38d6  ldarg.2
0x38d7  ldloc.s  0x14
0x38d9  ldloc.s  0x12
0x38db  call     void [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV2(class [Owin]Owin.IAppBuilder, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory, class [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator)
0x38e0  ret
```
