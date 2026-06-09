# Microsoft.Reporting.WebForms.ReportControlSession::DeliverReportItem

- ea: `0x11670`
- end: `0x117cd`
- name: `Microsoft.Reporting.WebForms.ReportControlSession::DeliverReportItem`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3b760`

## callees

- `0x1ae0`
- `0x2d70`
- `0x5040`
- `0x11670`
- `0x11820`
- `0x24dd0`

## string_xrefs

- `0x116ac`: `<ScheduleDefinition xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><StartDateTime xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer">{0}</StartDateTime>{1}</ScheduleDefinition>`
- `0x116e1`: `<ScheduleDefinition xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><StartDateTime xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer">{0}</StartDateTime>{1}</ScheduleDefinition>`
- `0x1170e`: `<ScheduleDefinition xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><StartDateTime xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer">{0}</StartDateTime>{1}</ScheduleDefinition>`
- `0x116c7`: `<MinuteRecurrence xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer"><MinutesInterval>60</MinutesInterval></MinuteRecurrence>`
- `0x116fc`: `<DailyRecurrence xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer"><DaysInterval>1</DaysInterval></DailyRecurrence>`
- `0x1172e`: `<WeeklyRecurrence xmlns="http://schemas.microsoft.com/sqlserver/reporting/2010/03/01/ReportServer"><WeeksInterval>1</WeeksInterval><DaysOfWeek><{0}>true</{0}></DaysOfWeek></WeeklyRecurrence>`
- `0x1174c`: `frequencyOfUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x11670  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11675  stloc.0
0x11676  ldnull
0x11677  stloc.1
0x11678  ldarg.s  5
0x1167a  ldstr    aHourly// "Hourly"
0x1167f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11684  brtrue.s loc_116A7
0x11686  ldarg.s  5
0x11688  ldstr    aDaily// "Daily"
0x1168d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11692  brtrue.s loc_116DC
0x11694  ldarg.s  5
0x11696  ldstr    aWeekly// "Weekly"
0x1169b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x116a0  brtrue.s loc_11709
0x116a2  br       loc_1174C
0x116a7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x116ac  ldstr    aScheduledefini// "<ScheduleDefinition xmlns:xsd=\"http://"...
0x116b1  ldloca.s 0
0x116b3  ldstr    aS// "s"
0x116b8  call     instance string [mscorlib]System.DateTime::ToString(string)
0x116bd  ldstr    aZ// "Z"
0x116c2  call     string [mscorlib]System.String::Concat(string, string)
0x116c7  ldstr    aMinuterecurren// "<MinuteRecurrence xmlns=\"http://schema"...
0x116cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x116d1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x116d6  stloc.1
0x116d7  br       loc_1175C
0x116dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x116e1  ldstr    aScheduledefini// "<ScheduleDefinition xmlns:xsd=\"http://"...
0x116e6  ldloca.s 0
0x116e8  ldstr    aS// "s"
0x116ed  call     instance string [mscorlib]System.DateTime::ToString(string)
0x116f2  ldstr    aZ// "Z"
0x116f7  call     string [mscorlib]System.String::Concat(string, string)
0x116fc  ldstr    aDailyrecurrenc// "<DailyRecurrence xmlns=\"http://schemas"...
0x11701  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x11706  stloc.1
0x11707  br.s     loc_1175C
0x11709  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1170e  ldstr    aScheduledefini// "<ScheduleDefinition xmlns:xsd=\"http://"...
0x11713  ldloca.s 0
0x11715  ldstr    aS// "s"
0x1171a  call     instance string [mscorlib]System.DateTime::ToString(string)
0x1171f  ldstr    aZ// "Z"
0x11724  call     string [mscorlib]System.String::Concat(string, string)
0x11729  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1172e  ldstr    aWeeklyrecurren// "<WeeklyRecurrence xmlns=\"http://schema"...
0x11733  ldloca.s 0
0x11735  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0x1173a  box      [mscorlib]System.DayOfWeek
0x1173f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x11744  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x11749  stloc.1
0x1174a  br.s     loc_1175C
0x1174c  ldstr    aFrequencyofupd// "frequencyOfUpdate"
0x11751  call     string Microsoft.Reporting.WebForms.Strings::InvalidUrlParameter(string paramName)
0x11756  newobj   instance void Microsoft.Reporting.WebForms.HttpHandlerInputException::.ctor(string message)
0x1175b  throw
0x1175c  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x11761  stloc.2
0x11762  ldloc.2
0x11763  ldstr    aDashboardid// "DashboardID"
0x11768  ldarg.3
0x11769  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x1176e  ldloc.2
0x1176f  ldstr    aReportvisualna// "ReportVisualName"
0x11774  ldarg.1
0x11775  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x1177a  ldloc.2
0x1177b  ldstr    aDashboardname// "DashboardName"
0x11780  ldarg.s  4
0x11782  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x11787  ldloc.2
0x11788  ldstr    aGroupid// "GroupID"
0x1178d  ldarg.2
0x1178e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x11793  ldloc.2
0x11794  ldstr    aContenttype// "ContentType"
0x11799  ldstr    aVisual// "Visual"
0x1179e  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x117a3  ldstr    aReportServerPo// "Report Server PowerBI"
0x117a8  ldloc.2
0x117a9  newobj   instance void Microsoft.Reporting.WebForms.ExtensionSettings::.ctor(string name, class [System]System.Collections.Specialized.NameValueCollection extensionParameters)
0x117ae  stloc.3
0x117af  ldarg.0
0x117b0  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportControlSession::get_Report()
0x117b5  ldstr    aImage_0// "IMAGE"
0x117ba  ldnull
0x117bb  ldloc.3
0x117bc  ldsfld   string [mscorlib]System.String::Empty
0x117c1  ldstr    aTimedsubscript// "TimedSubscription"
0x117c6  ldloc.1
0x117c7  callvirt instance void Microsoft.Reporting.WebForms.Report::InternalDeliverReportItem(string format, string deviceInfo, class Microsoft.Reporting.WebForms.ExtensionSettings settings, string description, string eventType, string matchData)
0x117cc  ret
```
