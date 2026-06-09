# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI

- ea: `0xee70`
- end: `0xef75`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI`
- size: `261`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x80c0`
- `0x8280`
- `0x8320`
- `0x1fb70`

## callees

- `0xee70`
- `0xf060`
- `0xf470`

## pseudocode

```c

```

## disassembly

```asm
0xee70  ldarg.0
0xee71  brtrue.s loc_EE7E
0xee73  ldstr    aSoapschedule// "soapSchedule"
0xee78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xee7d  throw
0xee7e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::.ctor()
0xee83  dup
0xee84  ldarg.0
0xee85  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_ScheduleID()
0xee8a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xee8f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Id(valuetype [mscorlib]System.Guid)
0xee94  dup
0xee95  ldarg.0
0xee96  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_Name()
0xee9b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Name(string)
0xeea0  dup
0xeea1  ldarg.0
0xeea2  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_Definition()
0xeea7  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition soapDefinition)
0xeeac  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Definition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition)
0xeeb1  dup
0xeeb2  ldarg.0
0xeeb3  ldarg.1
0xeeb4  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::GetDescription(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule soapSchedule, int32 utcOffsetInMinutes)
0xeeb9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Description(string)
0xeebe  dup
0xeebf  ldarg.0
0xeec0  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_Creator()
0xeec5  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_Creator(string)
0xeeca  dup
0xeecb  ldarg.0
0xeecc  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_NextRunTime()
0xeed1  stloc.0
0xeed2  ldloca.s 0
0xeed4  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xeed9  brfalse.s loc_EEE8
0xeedb  ldarg.0
0xeedc  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_NextRunTime()
0xeee1  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xeee6  br.s     loc_EEF1
0xeee8  ldloca.s 1
0xeeea  initobj  [mscorlib]System.DateTimeOffset
0xeef0  ldloc.1
0xeef1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_NextRunTime(valuetype [mscorlib]System.DateTimeOffset)
0xeef6  dup
0xeef7  ldarg.0
0xeef8  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_NextRunTimeSpecified()
0xeefd  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_NextRunTimeSpecified(bool)
0xef02  dup
0xef03  ldarg.0
0xef04  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_LastRunTime()
0xef09  stloc.0
0xef0a  ldloca.s 0
0xef0c  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xef11  brfalse.s loc_EF20
0xef13  ldarg.0
0xef14  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_LastRunTime()
0xef19  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xef1e  br.s     loc_EF29
0xef20  ldloca.s 1
0xef22  initobj  [mscorlib]System.DateTimeOffset
0xef28  ldloc.1
0xef29  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_LastRunTime(valuetype [mscorlib]System.DateTimeOffset)
0xef2e  dup
0xef2f  ldarg.0
0xef30  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_LastRunTimeSpecified()
0xef35  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_LastRunTimeSpecified(bool)
0xef3a  dup
0xef3b  ldarg.0
0xef3c  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_ReferencesPresent()
0xef41  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_ReferencesPresent(bool)
0xef46  dup
0xef47  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleStateEnum
0xef4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xef51  ldarg.0
0xef52  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleStateEnum [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Schedule::get_State()
0xef57  stloc.2
0xef58  ldloca.s 2
0xef5a  constrained. [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleStateEnum
0xef60  callvirt instance string [mscorlib]System.Object::ToString()
0xef65  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xef6a  unbox.any [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleStateEnum
0xef6f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Schedule::set_State(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleStateEnum)
0xef74  ret
```
