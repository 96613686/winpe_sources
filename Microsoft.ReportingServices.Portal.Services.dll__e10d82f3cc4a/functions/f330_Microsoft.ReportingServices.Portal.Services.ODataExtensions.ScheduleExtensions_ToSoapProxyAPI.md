# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapProxyAPI

- ea: `0xf330`
- end: `0xf43f`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapProxyAPI`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xf750`

## callees

- `0xa940`
- `0xf330`
- `0xf4b0`
- `0x22090`
- `0x220f0`

## pseudocode

```c

```

## disassembly

```asm
0xf330  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xf335  stloc.0
0xf336  ldloc.0
0xf337  ldarg.0
0xf338  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass7_0::webApiSchedule
0xf33d  ldloc.0
0xf33e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass7_0::webApiSchedule
0xf343  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleRecurrence [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_Recurrence()
0xf348  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf34d  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xf352  ldloc.0
0xf353  ldftn    instance bool <>c__DisplayClass7_0::<ToSoapProxyAPI>b__0(class [mscorlib]System.Reflection.PropertyInfo p)
0xf359  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, bool>::.ctor(object, native int)
0xf35e  call     T0x2B0000CB
0xf363  ldloc.0
0xf364  ldftn    instance object <>c__DisplayClass7_0::<ToSoapProxyAPI>b__1(class [mscorlib]System.Reflection.PropertyInfo p)
0xf36a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, object>::.ctor(object, native int)
0xf36f  call     T0x2B0000CC
0xf374  call     T0x2B0000CD
0xf379  stloc.1
0xf37a  ldloc.1
0xf37b  call     T0x2B0000CE
0xf380  ldc.i4.1
0xf381  ble.s    loc_F395
0xf383  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_InvalidScheduleRecurrenceObject()
0xf388  ldc.i4   0x190
0xf38d  ldc.i4.s 0x66
0xf38f  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException::.ctor(string, valuetype [System]System.Net.HttpStatusCode, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0xf394  throw
0xf395  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition::.ctor()
0xf39a  dup
0xf39b  ldloc.0
0xf39c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass7_0::webApiSchedule
0xf3a1  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_StartDateTime()
0xf3a6  stloc.3
0xf3a7  ldloca.s 3
0xf3a9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_DateTime()
0xf3ae  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition::set_StartDateTime(valuetype [mscorlib]System.DateTime)
0xf3b3  dup
0xf3b4  ldloc.0
0xf3b5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass7_0::webApiSchedule
0xf3ba  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_EndDate()
0xf3bf  stloc.3
0xf3c0  ldloca.s 3
0xf3c2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_DateTime()
0xf3c7  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition::set_EndDate(valuetype [mscorlib]System.DateTime)
0xf3cc  dup
0xf3cd  ldloc.0
0xf3ce  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass7_0::webApiSchedule
0xf3d3  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_EndDateSpecified()
0xf3d8  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition::set_EndDateSpecified(bool)
0xf3dd  stloc.2
0xf3de  ldloc.1
0xf3df  call     T0x2B0000CF
0xf3e4  brfalse.s loc_F43D
0xf3e6  newobj   instance void <>c__DisplayClass7_1::.ctor()
0xf3eb  stloc.s  4
0xf3ed  ldloc.1
0xf3ee  call     T0x2B0000D1
0xf3f3  stloc.s  5
0xf3f5  ldloc.s  4
0xf3f7  ldloc.1
0xf3f8  call     T0x2B0000D1
0xf3fd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf402  stfld    class [mscorlib]System.Type <>c__DisplayClass7_1::recurrenceType
0xf407  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::OccurenceTypeMap
0xf40c  ldloc.s  4
0xf40e  ldftn    instance bool <>c__DisplayClass7_1::<ToSoapProxyAPI>b__2(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type> p)
0xf414  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool>::.ctor(object, native int)
0xf419  call     T0x2B0000D2
0xf41e  stloc.s  7
0xf420  ldloca.s 7
0xf422  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::get_Key()
0xf427  stloc.s  6
0xf429  ldloc.2
0xf42a  ldloc.s  5
0xf42c  ldloc.s  6
0xf42e  call     object Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo(object source, class [mscorlib]System.Type type)
0xf433  castclass [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.RecurrencePattern
0xf438  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition::set_Item(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.RecurrencePattern)
0xf43d  ldloc.2
0xf43e  ret
```
