# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::IsUpdateRequired

- ea: `0x4a0`
- end: `0x5f5`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::IsUpdateRequired`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2f0`

## callees

- `0x40`
- `0x60`
- `0x80`
- `0x4a0`
- `0x600`
- `0x660`

## string_xrefs

- `0x4a4`: `Create DB`
- `0x512`: `\n        A database used in Power BI Report Server will not be able to attach back to SQL Server Reporting Services.`
- `0x531`: `\n        The database was created by a higher edition of Report Server product, some features may become unsupported in runtime.`

## pseudocode

```c

```

## disassembly

```asm
0x4a0  ldarg.0
0x4a1  brtrue.s loc_4B1
0x4a3  ldc.i4.5
0x4a4  ldstr    aCreateDb// "Create DB"
0x4a9  ldarg.0
0x4aa  ldarg.1
0x4ab  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x4b0  ret
0x4b1  ldarg.1
0x4b2  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x4b7  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x4bc  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x4c1  ldc.i4.1
0x4c2  bne.un.s loc_4E5
0x4c4  ldarg.0
0x4c5  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x4ca  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x4cf  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x4d4  ldc.i4.2
0x4d5  bne.un.s loc_4E5
0x4d7  ldc.i4.3
0x4d8  ldstr    aAttachingPbiTo// "Attaching PBI to RS"
0x4dd  ldarg.0
0x4de  ldarg.1
0x4df  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x4e4  ret
0x4e5  ldstr    asc_220E// ""
0x4ea  stloc.0
0x4eb  ldarg.0
0x4ec  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x4f1  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x4f6  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x4fb  ldc.i4.1
0x4fc  bne.un.s loc_51D
0x4fe  ldarg.1
0x4ff  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x504  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x509  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x50e  ldc.i4.2
0x50f  bne.un.s loc_51D
0x511  ldloc.0
0x512  ldstr    aADatabaseUsedI// "\n        A database used in Power BI R"...
0x517  call     string [mscorlib]System.String::Concat(string, string)
0x51c  stloc.0
0x51d  ldarg.1
0x51e  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x523  ldarg.0
0x524  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x529  call     bool [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuUtils::SkuSupportsDatabasesCreatedBy(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x52e  brtrue.s loc_53C
0x530  ldloc.0
0x531  ldstr    aTheDatabaseWas// "\n        The database was created by a"...
0x536  call     string [mscorlib]System.String::Concat(string, string)
0x53b  stloc.0
0x53c  ldarg.0
0x53d  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_BuildNumber()
0x542  call     class [mscorlib]System.Version [mscorlib]System.Version::Parse(string)
0x547  stloc.1
0x548  ldarg.1
0x549  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_BuildNumber()
0x54e  call     class [mscorlib]System.Version [mscorlib]System.Version::Parse(string)
0x553  stloc.2
0x554  ldarg.0
0x555  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_DbSchemaHash()
0x55a  ldarg.1
0x55b  callvirt instance string Microsoft.BIServer.Management.WebApi.ProductInfo::get_DbSchemaHash()
0x560  call     bool [mscorlib]System.String::op_Equality(string, string)
0x565  brfalse.s loc_5C4
0x567  ldarg.0
0x568  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x56d  ldarg.1
0x56e  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x573  beq.s    loc_5B0
0x575  ldloc.0
0x576  ldstr    aTheDatabaseWil// "\n        The database will change SKU "...
0x57b  ldarg.0
0x57c  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x581  box      [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType
0x586  ldarg.1
0x587  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType Microsoft.BIServer.Management.WebApi.ProductInfo::get_ServerSku()
0x58c  box      [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType
0x591  call     string [mscorlib]System.String::Format(string, object, object)
0x596  call     string [mscorlib]System.String::Concat(string, string)
0x59b  stloc.0
0x59c  ldc.i4.5
0x59d  ldstr    aTrivialUpgrade// "Trivial Upgrade: "
0x5a2  ldloc.0
0x5a3  call     string [mscorlib]System.String::Concat(string, string)
0x5a8  ldloc.1
0x5a9  ldloc.2
0x5aa  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x5af  ret
0x5b0  ldc.i4.2
0x5b1  ldstr    aValid// "Valid: "
0x5b6  ldloc.0
0x5b7  call     string [mscorlib]System.String::Concat(string, string)
0x5bc  ldloc.1
0x5bd  ldloc.2
0x5be  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x5c3  ret
0x5c4  ldloc.2
0x5c5  ldloc.1
0x5c6  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x5cb  brfalse.s loc_5E1
0x5cd  ldc.i4.5
0x5ce  ldstr    aTrivialUpgrade// "Trivial Upgrade: "
0x5d3  ldloc.0
0x5d4  call     string [mscorlib]System.String::Concat(string, string)
0x5d9  ldloc.1
0x5da  ldloc.2
0x5db  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::InfoResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x5e0  ret
0x5e1  ldc.i4.4
0x5e2  ldstr    aDetectedDowngr// "Detected Downgrade: "
0x5e7  ldloc.0
0x5e8  call     string [mscorlib]System.String::Concat(string, string)
0x5ed  ldloc.1
0x5ee  ldloc.2
0x5ef  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpdateRulesEngine::WarnResult(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus status, string context, object versionDatabase, object versionCode)
0x5f4  ret
```
