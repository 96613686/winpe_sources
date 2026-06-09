# Microsoft.BIServer.BIService.BIService::UpdateManagedProcessConfigs

- ea: `0x10e0`
- end: `0x12ab`
- name: `Microsoft.BIServer.BIService.BIService::UpdateManagedProcessConfigs`
- size: `459`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xfb0`
- `0x3390`

## callees

- `0x9d0`
- `0x10e0`
- `0x12b0`
- `0x2190`
- `0x21a0`
- `0x2320`
- `0x2350`
- `0x2360`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0x10e5  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x10ea  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0x10ef  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0x10f4  stloc.0
0x10f5  ldnull
0x10f6  ldloc.0
0x10f7  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x10fc  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x1101  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x1106  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType)
0x110b  callvirt instance string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::get_ShortName()
0x1110  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.InstanceId::.ctor(string)
0x1115  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x111a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Applications()
0x111f  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.UrlApplications [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.UrlEndpoints::GetAllRegisteredEndpoints(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.InstanceId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application>)
0x1124  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Uri>::.ctor()
0x1129  stloc.1
0x112a  ldarg.1
0x112b  callvirt instance string Microsoft.BIServer.BIService.ServiceConfig::get_RsConfigFilePath()
0x1130  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::.ctor(string)
0x1135  stloc.2
0x1136  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.UrlApplications::get_Values()
0x113b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application>::GetEnumerator()
0x1140  stloc.3
0x1141  br.s     loc_118E
0x1143  ldloc.3
0x1144  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application>::get_Current()
0x1149  stloc.s  4
0x114b  ldloc.s  4
0x114d  ldloc.2
0x114e  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x1153  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_ReportServerUrlOverride()
0x1158  ldloc.2
0x1159  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x115e  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_PortalUrlOverride()
0x1163  ldloc.2
0x1164  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x1169  callvirt instance int32 [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_SecureConnectionLevel()
0x116e  call     class [System]System.Uri [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ExternalUrlHelpers::CalculateUrl(class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application, string, string, int32)
0x1173  stloc.s  5
0x1175  ldloc.s  5
0x1177  ldnull
0x1178  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x117d  brfalse.s loc_118E
0x117f  ldloc.1
0x1180  ldloc.s  4
0x1182  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Application::get_Name()
0x1187  ldloc.s  5
0x1189  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Uri>::Add(var<u1>, !!T0)
0x118e  ldloc.3
0x118f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1194  brtrue.s loc_1143
0x1196  leave.s  loc_11A2
0x1198  ldloc.3
0x1199  brfalse.s loc_11A1
0x119b  ldloc.3
0x119c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11a1  endfinally
0x11a2  ldarg.2
0x11a3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::RsConfigSwitches
0x11a8  ldarg.1
0x11a9  callvirt instance string Microsoft.BIServer.BIService.ServiceConfig::get_RsConfigFilePath()
0x11ae  ldarg.2
0x11af  ldloc.1
0x11b0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::FormatForProcessConfig(class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>, string, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Uri>)
0x11b5  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x11ba  stloc.s  6
0x11bc  br.s     loc_11E0
0x11be  ldloca.s 6
0x11c0  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x11c5  stloc.s  7
0x11c7  ldarg.1
0x11c8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties()
0x11cd  ldloca.s 7
0x11cf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x11d4  ldloca.s 7
0x11d6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x11db  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x11e0  ldloca.s 6
0x11e2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x11e7  brtrue.s loc_11BE
0x11e9  leave.s  loc_11F9
0x11eb  ldloca.s 6
0x11ed  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x11f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11f8  endfinally
0x11f9  ldarg.0
0x11fa  ldarg.1
0x11fb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties()
0x1200  call     instance void Microsoft.BIServer.BIService.BIService::AddLoggerConfigValuesToServiceProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> properties)
0x1205  ldarg.1
0x1206  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0x120b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.BIService.ProcessConfig>::GetEnumerator()
0x1210  stloc.s  8
0x1212  br.s     loc_1290
0x1214  ldloc.s  8
0x1216  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.BIService.ProcessConfig>::get_Current()
0x121b  stloc.s  9
0x121d  ldloc.s  9
0x121f  ldc.i4.7
0x1220  newarr   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>
0x1225  dup
0x1226  ldc.i4.0
0x1227  call     class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigDefaults::get_Current()
0x122c  stelem.ref
0x122d  dup
0x122e  ldc.i4.1
0x122f  call     class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitchDefaults::get_Current()
0x1234  stelem.ref
0x1235  dup
0x1236  ldc.i4.2
0x1237  ldarg.2
0x1238  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::ConfigurationInfo
0x123d  stelem.ref
0x123e  dup
0x123f  ldc.i4.3
0x1240  ldarg.1
0x1241  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties()
0x1246  stelem.ref
0x1247  dup
0x1248  ldc.i4.4
0x1249  ldloc.s  9
0x124b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x1250  stelem.ref
0x1251  dup
0x1252  ldc.i4.5
0x1253  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x1258  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::ReadKeyValueSettings()
0x125d  stelem.ref
0x125e  dup
0x125f  ldc.i4.6
0x1260  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1265  dup
0x1266  ldstr    aHostingDatabas// "Hosting-databaseValidationStatus"
0x126b  ldarg.2
0x126c  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_DatabaseValidationStatus()
0x1271  stloc.s  0xA
0x1273  ldloca.s 0xA
0x1275  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0x127b  callvirt instance string [mscorlib]System.Object::ToString()
0x1280  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1285  stelem.ref
0x1286  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeRightMostWins(class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>[] sources)
0x128b  callvirt instance void Microsoft.BIServer.BIService.ProcessConfig::set_Config(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x1290  ldloc.s  8
0x1292  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1297  brtrue   loc_1214
0x129c  leave.s  loc_12AA
0x129e  ldloc.s  8
0x12a0  brfalse.s loc_12A9
0x12a2  ldloc.s  8
0x12a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12a9  endfinally
0x12aa  ret
```
