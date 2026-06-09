# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::.ctor_0

- ea: `0x1880`
- end: `0x1974`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::.ctor_0`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1860`

## callees

- `0x1880`

## string_xrefs

- `0x18bb`: `systemService`
- `0x18d8`: `portalConfigurationManager`
- `0x18ec`: `portalConfigurationManager.Current`
- `0x18fb`: `dataModelRoleAccessor`

## pseudocode

```c

```

## disassembly

```asm
0x1880  ldarg.0
0x1881  ldc.i4.3
0x1882  newarr   [mscorlib]System.String
0x1887  dup
0x1888  ldc.i4.0
0x1889  ldstr    aHttp// "HTTP://"
0x188e  stelem.ref
0x188f  dup
0x1890  ldc.i4.1
0x1891  ldstr    aHttps// "HTTPS://"
0x1896  stelem.ref
0x1897  dup
0x1898  ldc.i4.2
0x1899  ldstr    aMailto// "MAILTO:"
0x189e  stelem.ref
0x189f  stfld    string[] Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_allowedUrlPrefixes
0x18a4  ldarg.0
0x18a5  call     instance void [mscorlib]System.Object::.ctor()
0x18aa  ldarg.1
0x18ab  brtrue.s loc_18B8
0x18ad  ldstr    aSoapproxy// "soapProxy"
0x18b2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18b7  throw
0x18b8  ldarg.2
0x18b9  brtrue.s loc_18C6
0x18bb  ldstr    aSystemservice// "systemService"
0x18c0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18c5  throw
0x18c6  ldarg.3
0x18c7  brtrue.s loc_18D4
0x18c9  ldstr    aLogger// "logger"
0x18ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18d3  throw
0x18d4  ldarg.s  4
0x18d6  brtrue.s loc_18E3
0x18d8  ldstr    aPortalconfigur// "portalConfigurationManager"
0x18dd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18e2  throw
0x18e3  ldarg.s  4
0x18e5  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x18ea  brtrue.s loc_18F7
0x18ec  ldstr    aPortalconfigur_0// "portalConfigurationManager.Current"
0x18f1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18f6  throw
0x18f7  ldarg.s  5
0x18f9  brtrue.s loc_1906
0x18fb  ldstr    aDatamodelrolea// "dataModelRoleAccessor"
0x1900  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1905  throw
0x1906  ldarg.0
0x1907  ldarg.1
0x1908  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_soapRS2010Proxy
0x190d  ldarg.0
0x190e  ldarg.2
0x190f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x1914  ldarg.0
0x1915  ldarg.3
0x1916  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x191b  ldarg.0
0x191c  ldarg.s  5
0x191e  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1923  ldarg.0
0x1924  ldarg.s  6
0x1926  dup
0x1927  brtrue.s loc_192F
0x1929  pop
0x192a  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.CatalogDataAccessor::.ctor()
0x192f  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x1934  ldarg.0
0x1935  ldarg.s  7
0x1937  dup
0x1938  brtrue.s loc_1940
0x193a  pop
0x193b  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.CatalogDataModelDataSourceAccessor::.ctor()
0x1940  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x1945  ldarg.0
0x1946  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.SubscriptionHistoryDataAccessor::.ctor()
0x194b  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ISubscriptionHistoryDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_subscriptionHistoryAccessor
0x1950  ldarg.0
0x1951  ldarg.s  4
0x1953  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0x1958  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_FileSizeRestrictions()
0x195d  stfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_fileSizeRestrictions
0x1962  ldarg.0
0x1963  ldarg.s  8
0x1965  dup
0x1966  brtrue.s loc_196E
0x1968  pop
0x1969  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.SymmetricKeyCrypto::get_Instance()
0x196e  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_crypto
0x1973  ret
```
