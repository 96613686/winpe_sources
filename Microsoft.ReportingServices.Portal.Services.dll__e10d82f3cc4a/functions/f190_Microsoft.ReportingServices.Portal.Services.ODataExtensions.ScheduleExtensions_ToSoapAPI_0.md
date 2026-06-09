# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI_0

- ea: `0xf190`
- end: `0xf324`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToSoapAPI_0`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xef80`
- `0xf490`
- `0xf710`

## callees

- `0xa940`
- `0xf190`
- `0xf4b0`
- `0x21ff0`
- `0x22050`

## pseudocode

```c

```

## disassembly

```asm
0xf190  newobj   instance void <>c__DisplayClass6_0::.ctor()
0xf195  stloc.0
0xf196  ldloc.0
0xf197  ldarg.0
0xf198  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass6_0::webApiSchedule
0xf19d  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::.ctor()
0xf1a2  dup
0xf1a3  ldloc.0
0xf1a4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass6_0::webApiSchedule
0xf1a9  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_StartDateTime()
0xf1ae  stloc.3
0xf1af  ldloca.s 3
0xf1b1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_LocalDateTime()
0xf1b6  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::set_StartDateTime(valuetype [mscorlib]System.DateTime)
0xf1bb  dup
0xf1bc  ldloc.0
0xf1bd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass6_0::webApiSchedule
0xf1c2  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_EndDate()
0xf1c7  stloc.3
0xf1c8  ldloca.s 3
0xf1ca  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_LocalDateTime()
0xf1cf  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::set_EndDate(valuetype [mscorlib]System.DateTime)
0xf1d4  dup
0xf1d5  ldloc.0
0xf1d6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass6_0::webApiSchedule
0xf1db  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_EndDateSpecified()
0xf1e0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::set_EndDateSpecified(bool)
0xf1e5  stloc.1
0xf1e6  ldloc.0
0xf1e7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition <>c__DisplayClass6_0::webApiSchedule
0xf1ec  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleRecurrence [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_Recurrence()
0xf1f1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf1f6  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xf1fb  ldloc.0
0xf1fc  ldftn    instance bool <>c__DisplayClass6_0::<ToSoapAPI>b__0(class [mscorlib]System.Reflection.PropertyInfo p)
0xf202  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, bool>::.ctor(object, native int)
0xf207  call     T0x2B0000CB
0xf20c  ldloc.0
0xf20d  ldftn    instance object <>c__DisplayClass6_0::<ToSoapAPI>b__1(class [mscorlib]System.Reflection.PropertyInfo p)
0xf213  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, object>::.ctor(object, native int)
0xf218  call     T0x2B0000CC
0xf21d  call     T0x2B0000CD
0xf222  stloc.2
0xf223  ldloc.2
0xf224  call     T0x2B0000CE
0xf229  ldc.i4.1
0xf22a  ble.s    loc_F23E
0xf22c  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_InvalidScheduleRecurrenceObject()
0xf231  ldc.i4   0x190
0xf236  ldc.i4.s 0x66
0xf238  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException::.ctor(string, valuetype [System]System.Net.HttpStatusCode, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0xf23d  throw
0xf23e  ldloc.2
0xf23f  call     T0x2B0000CF
0xf244  brfalse  loc_F322
0xf249  newobj   instance void <>c__DisplayClass6_1::.ctor()
0xf24e  stloc.s  4
0xf250  ldloc.2
0xf251  call     T0x2B0000D0
0xf256  stloc.s  5
0xf258  ldloc.s  4
0xf25a  ldloc.2
0xf25b  call     T0x2B0000D1
0xf260  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf265  stfld    class [mscorlib]System.Type <>c__DisplayClass6_1::recurrenceType
0xf26a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::OccurenceTypeMap
0xf26f  ldloc.s  4
0xf271  ldftn    instance bool <>c__DisplayClass6_1::<ToSoapAPI>b__2(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type> p)
0xf277  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool>::.ctor(object, native int)
0xf27c  call     T0x2B0000D2
0xf281  stloc.s  8
0xf283  ldloca.s 8
0xf285  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::get_Key()
0xf28a  stloc.s  6
0xf28c  ldloc.1
0xf28d  ldloc.s  5
0xf28f  ldloc.s  6
0xf291  call     object Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo(object source, class [mscorlib]System.Type type)
0xf296  castclass [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern
0xf29b  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf2a0  ldloc.1
0xf2a1  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf2a6  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence
0xf2ab  stloc.s  7
0xf2ad  ldloc.s  7
0xf2af  brfalse.s loc_F2F4
0xf2b1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0xf2b6  stloc.s  9
0xf2b8  ldloc.s  9
0xf2ba  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf2bf  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xf2c4  ldsfld   string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::InvariantListSeparator
0xf2c9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf2ce  brfalse.s loc_F2F4
0xf2d0  ldloc.s  7
0xf2d2  ldloc.s  7
0xf2d4  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence::get_Days()
0xf2d9  ldsfld   string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::InvariantListSeparator
0xf2de  ldloc.s  9
0xf2e0  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf2e5  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xf2ea  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xf2ef  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence::set_Days(string)
0xf2f4  ldloc.1
0xf2f5  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf2fa  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MinuteRecurrence
0xf2ff  dup
0xf300  brtrue.s loc_F306
0xf302  pop
0xf303  ldc.i4.0
0xf304  br.s     loc_F30E
0xf306  call     instance int32 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MinuteRecurrence::get_MinutesInterval()
0xf30b  ldc.i4.1
0xf30c  clt
0xf30e  brfalse.s loc_F322
0xf310  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_InvalidScheduleRecurrenceObject()
0xf315  ldc.i4   0x190
0xf31a  ldc.i4.s 0x66
0xf31c  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.PortalException::.ctor(string, valuetype [System]System.Net.HttpStatusCode, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0xf321  throw
0xf322  ldloc.1
0xf323  ret
```
