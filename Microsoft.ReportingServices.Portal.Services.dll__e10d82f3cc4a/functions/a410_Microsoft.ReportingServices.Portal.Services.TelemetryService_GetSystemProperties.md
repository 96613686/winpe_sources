# Microsoft.ReportingServices.Portal.Services.TelemetryService::GetSystemProperties

- ea: `0xa410`
- end: `0xa585`
- name: `Microsoft.ReportingServices.Portal.Services.TelemetryService::GetSystemProperties`
- size: `373`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0xa290`
- `0xa2b0`
- `0xa2d0`
- `0xa2f0`
- `0xa310`
- `0xa330`
- `0xa350`
- `0xa370`
- `0xa390`
- `0xa3b0`
- `0xa3d0`
- `0xa3f0`
- `0xa410`

## pseudocode

```c

```

## disassembly

```asm
0xa410  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::.ctor()
0xa415  stloc.0
0xa416  ldarg.0
0xa417  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryConfigurationFactory Microsoft.ReportingServices.Portal.Services.TelemetryService::_telemetryFactory
0xa41c  callvirt instance object [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryConfigurationFactory::Create()
0xa421  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ITelemetryConfiguration
0xa426  stloc.1
0xa427  ldloc.0
0xa428  ldloc.1
0xa429  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ITelemetryConfiguration::get_IsEnabled()
0xa42e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_IsEnabled(bool)
0xa433  ldloc.0
0xa434  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::get_IsEnabled()
0xa439  brfalse  loc_A583
0xa43e  ldloc.0
0xa43f  call     bool [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Helpers.TelemetryUtils::IsInternal()
0xa444  ldc.i4.0
0xa445  ceq
0xa447  stloc.3
0xa448  ldloca.s 3
0xa44a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa44f  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0xa454  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_ExternalUser(string)
0xa459  ldloc.0
0xa45a  ldloc.1
0xa45b  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ITelemetryConfiguration::get_IsPublicBuild()
0xa460  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_IsPublicBuild(bool)
0xa465  ldloc.0
0xa466  ldarg.0
0xa467  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.TelemetryService::_configManager
0xa46c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xa471  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_InstallationId()
0xa476  stloc.s  4
0xa478  ldloca.s 4
0xa47a  ldstr    aD// "D"
0xa47f  call     instance string [mscorlib]System.Guid::ToString(string)
0xa484  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_InstallationId(string)
0xa489  ldloc.0
0xa48a  call     string Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Build()
0xa48f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Build(string)
0xa494  ldloc.0
0xa495  call     string Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Host()
0xa49a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Host(string)
0xa49f  ldloc.0
0xa4a0  ldloc.1
0xa4a1  ldarg.1
0xa4a2  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0xa4a7  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ITelemetryConfiguration::GetSHA256Hash(string)
0xa4ac  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_HashedUserId(string)
0xa4b1  ldloc.0
0xa4b2  call     string Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Edition()
0xa4b7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Edition(string)
0xa4bc  ldarg.0
0xa4bd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.Services.TelemetryService::_configManager
0xa4c2  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xa4c7  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_AuthenticationTypes()
0xa4cc  stloc.2
0xa4cd  ldloc.0
0xa4ce  ldloca.s 2
0xa4d0  constrained. [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes
0xa4d6  callvirt instance string [mscorlib]System.Object::ToString()
0xa4db  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_AuthenticationTypes(string)
0xa4e0  ldloc.0
0xa4e1  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_NumberOfProcessors()
0xa4e6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_NumberOfProcessors(int32)
0xa4eb  ldloc.0
0xa4ec  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_NumberOfCores()
0xa4f1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_NumberOfCores(int32)
0xa4f6  ldloc.0
0xa4f7  call     bool Microsoft.ReportingServices.Portal.Services.TelemetryService::get_IsVirtualMachine()
0xa4fc  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_IsVirtualMachine(bool)
0xa501  ldloc.0
0xa502  call     string Microsoft.ReportingServices.Portal.Services.TelemetryService::get_MachineId()
0xa507  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_MachineId(string)
0xa50c  ldloc.0
0xa50d  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_CountInstances()
0xa512  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_CountInstances(int32)
0xa517  ldloc.0
0xa518  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Count14xInstances()
0xa51d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Count14xInstances(int32)
0xa522  ldloc.0
0xa523  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Count13xInstances()
0xa528  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Count13xInstances(int32)
0xa52d  ldloc.0
0xa52e  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Count12xInstances()
0xa533  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Count12xInstances(int32)
0xa538  ldloc.0
0xa539  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::get_Count11xInstances()
0xa53e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_Count11xInstances(int32)
0xa543  ldloc.0
0xa544  ldarg.0
0xa545  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Services.TelemetryService::_systemService
0xa54a  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xa54f  brtrue.s loc_A563
0xa551  ldc.i4.0
0xa552  stloc.s  5
0xa554  ldloca.s 5
0xa556  constrained. [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ProductSku
0xa55c  callvirt instance string [mscorlib]System.Object::ToString()
0xa561  br.s     loc_A573
0xa563  ldc.i4.1
0xa564  stloc.s  5
0xa566  ldloca.s 5
0xa568  constrained. [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ProductSku
0xa56e  callvirt instance string [mscorlib]System.Object::ToString()
0xa573  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_ProductSku(string)
0xa578  ldloc.0
0xa579  ldstr    a2// "2"
0xa57e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.TelemetryHostData::set_PortalVersion(string)
0xa583  ldloc.0
0xa584  ret
```
