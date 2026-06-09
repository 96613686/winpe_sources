# Microsoft.ReportingServices.Portal.Repositories.SystemService::PopulateScheduleDescription

- ea: `0x8320`
- end: `0x839e`
- name: `Microsoft.ReportingServices.Portal.Repositories.SystemService::PopulateScheduleDescription`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x82a0`
- `0x82e0`

## callees

- `0x80c0`
- `0x8320`
- `0xee70`
- `0xef80`

## pseudocode

```c

```

## disassembly

```asm
0x8320  ldnull
0x8321  stloc.0
0x8322  ldsfld   string [mscorlib]System.String::Empty
0x8327  stloc.1
0x8328  ldarg.2
0x8329  brfalse.s loc_8387
0x832b  ldarg.2
0x832c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_ScheduleID()
0x8331  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8336  brtrue.s loc_836D
0x8338  ldarg.0
0x8339  ldarg.1
0x833a  ldarg.2
0x833b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_ScheduleID()
0x8340  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8345  ldarg.3
0x8346  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule Microsoft.ReportingServices.Portal.Repositories.SystemService::GetSchedule(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid key, int32 utcOffsetInMinutes)
0x834b  stloc.0
0x834c  leave.s  loc_8387
0x834e  stloc.2
0x834f  ldarg.0
0x8350  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.SystemService::_logger
0x8355  ldc.i4.3
0x8356  ldstr    aMessage0// "Message: {0}"
0x835b  ldloc.2
0x835c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8361  call     string [mscorlib]System.String::Format(string, object)
0x8366  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x836b  leave.s  loc_8387
0x836d  ldarg.2
0x836e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_Definition()
0x8373  brfalse.s loc_8387
0x8375  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::.ctor()
0x837a  dup
0x837b  ldarg.2
0x837c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::get_Definition()
0x8381  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Definition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition)
0x8386  stloc.0
0x8387  ldloc.0
0x8388  brfalse.s loc_839C
0x838a  ldloc.0
0x838b  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule webApiSchedule)
0x8390  ldarg.3
0x8391  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule soapSchedule, [opt] int32 utcOffsetInMinutes)
0x8396  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Description()
0x839b  stloc.1
0x839c  ldloc.1
0x839d  ret
```
