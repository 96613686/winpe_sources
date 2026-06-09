# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI

- ea: `0xef80`
- end: `0xf05d`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI`
- size: `221`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8150`
- `0x81a0`
- `0x8280`
- `0x8320`

## callees

- `0xef80`
- `0xf190`

## pseudocode

```c

```

## disassembly

```asm
0xef80  ldarg.0
0xef81  brtrue.s loc_EF8E
0xef83  ldstr    aWebapischedule// "webApiSchedule"
0xef88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xef8d  throw
0xef8e  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::.ctor()
0xef93  dup
0xef94  ldarg.0
0xef95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Id()
0xef9a  stloc.0
0xef9b  ldloca.s 0
0xef9d  constrained. [mscorlib]System.Guid
0xefa3  callvirt instance string [mscorlib]System.Object::ToString()
0xefa8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_ScheduleID(string)
0xefad  dup
0xefae  ldarg.0
0xefaf  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Name()
0xefb4  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_Name(string)
0xefb9  dup
0xefba  ldarg.0
0xefbb  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Definition()
0xefc0  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition webApiSchedule)
0xefc5  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_Definition(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition)
0xefca  dup
0xefcb  ldarg.0
0xefcc  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Description()
0xefd1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_Description(string)
0xefd6  dup
0xefd7  ldarg.0
0xefd8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_Creator()
0xefdd  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_Creator(string)
0xefe2  dup
0xefe3  ldarg.0
0xefe4  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_NextRunTime()
0xefe9  stloc.1
0xefea  ldloca.s 1
0xefec  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_LocalDateTime()
0xeff1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_NextRunTime(valuetype [mscorlib]System.DateTime)
0xeff6  dup
0xeff7  ldarg.0
0xeff8  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_NextRunTimeSpecified()
0xeffd  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_NextRunTimeSpecified(bool)
0xf002  dup
0xf003  ldarg.0
0xf004  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_LastRunTime()
0xf009  stloc.1
0xf00a  ldloca.s 1
0xf00c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_LocalDateTime()
0xf011  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_LastRunTime(valuetype [mscorlib]System.DateTime)
0xf016  dup
0xf017  ldarg.0
0xf018  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_LastRunTimeSpecified()
0xf01d  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_LastRunTimeSpecified(bool)
0xf022  dup
0xf023  ldarg.0
0xf024  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_ReferencesPresent()
0xf029  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_ReferencesPresent(bool)
0xf02e  dup
0xf02f  ldtoken  [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleStateEnum
0xf034  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf039  ldarg.0
0xf03a  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleStateEnum [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::get_State()
0xf03f  stloc.2
0xf040  ldloca.s 2
0xf042  constrained. [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleStateEnum
0xf048  callvirt instance string [mscorlib]System.Object::ToString()
0xf04d  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xf052  unbox.any [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleStateEnum
0xf057  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::set_State(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleStateEnum)
0xf05c  ret
```
