# Microsoft.ReportingServices.Portal.Services.TelemetryService::.cctor

- ea: `0xa190`
- end: `0xa240`
- name: `Microsoft.ReportingServices.Portal.Services.TelemetryService::.cctor`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0xa2a0`
- `0xa2c0`
- `0xa2e0`
- `0xa300`
- `0xa320`
- `0xa340`
- `0xa360`
- `0xa380`
- `0xa3a0`
- `0xa3c0`
- `0xa3e0`
- `0xa400`
- `0xa590`
- `0xa5d0`
- `0xa670`
- `0xa6d0`
- `0xa730`

## pseudocode

```c

```

## disassembly

```asm
0xa190  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xa195  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0xa19a  call     valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::GetInstalledSku(string)
0xa19f  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0xa1a4  callvirt instance string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::get_ShortName()
0xa1a9  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Edition(string value)
0xa1ae  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xa1b3  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0xa1b8  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0xa1bd  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Host(string value)
0xa1c2  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xa1c7  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ServerProductVersion()
0xa1cc  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Build(string value)
0xa1d1  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfProcessors()
0xa1d6  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_NumberOfProcessors(int32 value)
0xa1db  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfCores()
0xa1e0  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_NumberOfCores(int32 value)
0xa1e5  call     bool Microsoft.ReportingServices.Portal.Services.TelemetryService::IsThisVirtualMachine()
0xa1ea  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_IsVirtualMachine(bool value)
0xa1ef  call     string [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Helpers.TelemetryUtils::GetMachineId()
0xa1f4  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_MachineId(string value)
0xa1f9  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfInstances()
0xa1fe  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_CountInstances(int32 value)
0xa203  ldstr    a11// "11"
0xa208  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfInstancesAtVersion(string versionStartsWith)
0xa20d  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Count11xInstances(int32 value)
0xa212  ldstr    a12// "12"
0xa217  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfInstancesAtVersion(string versionStartsWith)
0xa21c  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Count12xInstances(int32 value)
0xa221  ldstr    a13// "13"
0xa226  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfInstancesAtVersion(string versionStartsWith)
0xa22b  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Count13xInstances(int32 value)
0xa230  ldstr    a14// "14"
0xa235  call     int32 Microsoft.ReportingServices.Portal.Services.TelemetryService::GetNumberOfInstancesAtVersion(string versionStartsWith)
0xa23a  call     void Microsoft.ReportingServices.Portal.Services.TelemetryService::set_Count14xInstances(int32 value)
0xa23f  ret
```
