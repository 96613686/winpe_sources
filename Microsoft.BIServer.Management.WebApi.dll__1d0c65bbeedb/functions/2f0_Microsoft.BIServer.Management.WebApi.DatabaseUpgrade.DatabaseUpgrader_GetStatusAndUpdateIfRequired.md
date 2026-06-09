# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetStatusAndUpdateIfRequired

- ea: `0x2f0`
- end: `0x391`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetStatusAndUpdateIfRequired`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd60`

## callees

- `0x60`
- `0x80`
- `0x2f0`
- `0x3a0`
- `0x3c0`
- `0x3e0`
- `0x470`
- `0x4a0`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldarg.0
0x2f1  brtrue.s loc_2F5
0x2f3  ldc.i4.6
0x2f4  ret
0x2f5  ldarg.0
0x2f6  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess)
0x2fb  stloc.0
0x2fc  ldarg.0
0x2fd  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::get_DatabaseName()
0x302  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x307  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0x30c  call     class Microsoft.BIServer.Management.WebApi.ProductInfo Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromCode(string databaseName, string instanceId)
0x311  stloc.1
0x312  ldloc.0
0x313  call     class Microsoft.BIServer.Management.WebApi.ProductInfo Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromDatabase(class [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor productInfoDataAccessor)
0x318  ldloc.1
0x319  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::IsUpdateRequired(class Microsoft.BIServer.Management.WebApi.ProductInfo detailsOfSkuThatCreatedDb, class Microsoft.BIServer.Management.WebApi.ProductInfo detailsOfSkuThatIsInstalled)
0x31e  stloc.2
0x31f  ldloc.2
0x320  ldc.i4.5
0x321  bne.un.s loc_37D
0x323  ldstr    aUpgrading0Data// "Upgrading {0} database to version {1} h"...
0x328  ldc.i4.3
0x329  newarr   [mscorlib]System.Object
0x32e  dup
0x32f  ldc.i4.0
0x330  ldarg.0
0x331  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::get_DatabaseName()
0x336  stelem.ref
0x337  dup
0x338  ldc.i4.1
0x339  ldloc.1
0x33a  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_BuildNumber()
0x33f  stelem.ref
0x340  dup
0x341  ldc.i4.2
0x342  ldloc.1
0x343  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_DbSchemaHash()
0x348  stelem.ref
0x349  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x34e  ldarg.0
0x34f  call     void Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::UpgradeDatabase(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess sqlAccess)
0x354  ldloc.0
0x355  ldloc.1
0x356  call     void Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::SaveProductInfoToDatabase(class [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor productInfoDataAccessor, class Microsoft.BIServer.Management.WebApi.ProductInfo productInfoCode)
0x35b  ldloc.0
0x35c  call     class Microsoft.BIServer.Management.WebApi.ProductInfo Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromDatabase(class [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ProductInfoDataAccessor productInfoDataAccessor)
0x361  ldloc.1
0x362  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::IsUpdateRequired(class Microsoft.BIServer.Management.WebApi.ProductInfo detailsOfSkuThatCreatedDb, class Microsoft.BIServer.Management.WebApi.ProductInfo detailsOfSkuThatIsInstalled)
0x367  stloc.2
0x368  leave.s  loc_37D
0x36a  ldstr    aDatabaseUpgrad// "Database upgrade failed!!  The database"...
0x36f  call     T0x2B000002
0x374  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Fatal(class [mscorlib]System.Exception, string, object[])
0x379  ldc.i4.6
0x37a  stloc.3
0x37b  leave.s  loc_38F
0x37d  ldarg.0
0x37e  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess)
0x383  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::EnsureDefaults()
0x388  callvirt instance void [mscorlib]System.Threading.Tasks.Task::Wait()
0x38d  ldloc.2
0x38e  ret
0x38f  ldloc.3
0x390  ret
```
