# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::Upgrade

- ea: `0x43a0`
- end: `0x440d`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::Upgrade`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4410`
- `0x4500`
- `0x4670`
- `0x46d0`
- `0x4730`
- `0x4740`
- `0x47b0`

## string_xrefs

- `0x43ad`: `application/xhtml+xml`
- `0x43b8`: `image/svg+xml`
- `0x43c5`: `SQL Server Reporting Services`

## pseudocode

```c

```

## disassembly

```asm
0x43a0  ldarg.0
0x43a1  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddPngToListOfTrustedFileFormats(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> currentConfiguration)
0x43a6  ldarg.0
0x43a7  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::EnsureHtmlMimeTypeRestrictionMatchHtmlExtensionPolicy(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> currentConfiguration)
0x43ac  ldarg.0
0x43ad  ldstr    aApplicationXht// "application/xhtml+xml"
0x43b2  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddMimeTypeIfNotInRestrictedResourceMimeTypeForUpload(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string needAddMimeTypeValue)
0x43b7  ldarg.0
0x43b8  ldstr    aImageSvgXml// "image/svg+xml"
0x43bd  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::AddMimeTypeIfNotInRestrictedResourceMimeTypeForUpload(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string needAddMimeTypeValue)
0x43c2  ldarg.0
0x43c3  ldc.i4.s 0x15
0x43c5  ldstr    aSqlServerRepor// "SQL Server Reporting Services"
0x43ca  ldstr    aDefault// "Default"
0x43cf  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings key, string oldValue, string newValue)
0x43d4  ldarg.0
0x43d5  ldc.i4.1
0x43d6  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::OriginalCustomHeaders
0x43db  ldstr    aCustomheadersH// "<CustomHeaders> <Header> <Name>X-Frame-"...
0x43e0  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::UpdateSettingIfEqualsOldDefault(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings key, class [mscorlib]System.Collections.Generic.List`1<string> oldValues, string newValue)
0x43e5  ldarg.0
0x43e6  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemovePowerBIRegistration(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x43eb  ldarg.0
0x43ec  ldstr    aEnablepowerbir// "EnablePowerBIReportEmbeddedModels"
0x43f1  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x43f6  ldarg.0
0x43f7  ldstr    aEnablereportde// "EnableReportDesignClientDownload"
0x43fc  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4401  ldarg.0
0x4402  ldstr    aReportbuilderl// "ReportBuilderLaunchURL"
0x4407  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x440c  ret
```
