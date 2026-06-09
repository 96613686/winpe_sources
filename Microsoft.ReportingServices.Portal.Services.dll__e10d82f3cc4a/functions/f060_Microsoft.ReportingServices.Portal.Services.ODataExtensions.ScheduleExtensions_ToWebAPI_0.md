# Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI_0

- ea: `0xf060`
- end: `0xf18d`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ToWebAPI_0`
- size: `301`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xee70`
- `0xf6a0`
- `0x102e0`

## callees

- `0xf060`
- `0xf4b0`
- `0x21fb0`

## pseudocode

```c

```

## disassembly

```asm
0xf060  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::.ctor()
0xf065  dup
0xf066  ldarg.0
0xf067  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::get_StartDateTime()
0xf06c  stloc.1
0xf06d  ldloca.s 1
0xf06f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xf074  brfalse.s loc_F083
0xf076  ldarg.0
0xf077  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::get_StartDateTime()
0xf07c  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xf081  br.s     loc_F08C
0xf083  ldloca.s 2
0xf085  initobj  [mscorlib]System.DateTimeOffset
0xf08b  ldloc.2
0xf08c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::set_StartDateTime(valuetype [mscorlib]System.DateTimeOffset)
0xf091  dup
0xf092  ldarg.0
0xf093  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::get_EndDate()
0xf098  stloc.1
0xf099  ldloca.s 1
0xf09b  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xf0a0  brfalse.s loc_F0AF
0xf0a2  ldarg.0
0xf0a3  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::get_EndDate()
0xf0a8  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xf0ad  br.s     loc_F0B8
0xf0af  ldloca.s 2
0xf0b1  initobj  [mscorlib]System.DateTimeOffset
0xf0b7  ldloc.2
0xf0b8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::set_EndDate(valuetype [mscorlib]System.DateTimeOffset)
0xf0bd  dup
0xf0be  ldarg.0
0xf0bf  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::get_EndDateSpecified()
0xf0c4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::set_EndDateSpecified(bool)
0xf0c9  stloc.0
0xf0ca  ldarg.0
0xf0cb  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf0d0  brfalse  loc_F18B
0xf0d5  newobj   instance void <>c__DisplayClass5_0::.ctor()
0xf0da  stloc.3
0xf0db  ldarg.0
0xf0dc  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf0e1  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence
0xf0e6  stloc.s  4
0xf0e8  ldloc.s  4
0xf0ea  brfalse.s loc_F12F
0xf0ec  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_ClientPrimaryCulture()
0xf0f1  stloc.s  6
0xf0f3  ldloc.s  6
0xf0f5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf0fa  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xf0ff  ldsfld   string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::InvariantListSeparator
0xf104  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf109  brfalse.s loc_F12F
0xf10b  ldloc.s  4
0xf10d  ldloc.s  4
0xf10f  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence::get_Days()
0xf114  ldloc.s  6
0xf116  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xf11b  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_ListSeparator()
0xf120  ldsfld   string Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::InvariantListSeparator
0xf125  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xf12a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.MonthlyRecurrence::set_Days(string)
0xf12f  ldloc.3
0xf130  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type> Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::OccurenceTypeMap
0xf135  ldarg.0
0xf136  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf13b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf140  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::get_Item(void)
0xf145  stfld    class [mscorlib]System.Type <>c__DisplayClass5_0::targetType
0xf14a  ldarg.0
0xf14b  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.RecurrencePattern [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::Item
0xf150  ldloc.3
0xf151  ldfld    class [mscorlib]System.Type <>c__DisplayClass5_0::targetType
0xf156  call     object Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleExtensions::ConvertTo(object source, class [mscorlib]System.Type type)
0xf15b  stloc.s  5
0xf15d  ldloc.0
0xf15e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleRecurrence [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_Recurrence()
0xf163  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf168  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0xf16d  ldloc.3
0xf16e  ldftn    instance bool <>c__DisplayClass5_0::<ToWebAPI>b__0(class [mscorlib]System.Reflection.PropertyInfo p)
0xf174  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Reflection.PropertyInfo, bool>::.ctor(object, native int)
0xf179  call     T0x2B0000CA
0xf17e  ldloc.0
0xf17f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleRecurrence [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition::get_Recurrence()
0xf184  ldloc.s  5
0xf186  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0xf18b  ldloc.0
0xf18c  ret
```
