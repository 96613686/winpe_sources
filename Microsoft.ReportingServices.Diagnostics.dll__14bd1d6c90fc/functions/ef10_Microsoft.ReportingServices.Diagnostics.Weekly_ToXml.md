# Microsoft.ReportingServices.Diagnostics.Weekly::ToXml

- ea: `0xef10`
- end: `0xef52`
- name: `Microsoft.ReportingServices.Diagnostics.Weekly::ToXml`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xe7e0`
- `0xeaa0`
- `0xeeb0`
- `0xeed0`

## pseudocode

```c

```

## disassembly

```asm
0xef10  ldarg.1
0xef11  ldstr    aWeeklyrecurren// "WeeklyRecurrence"
0xef16  call     string Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace()
0xef1b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xef20  ldarg.1
0xef21  ldstr    aWeeksinterval// "WeeksInterval"
0xef26  ldarg.0
0xef27  call     instance int64 Microsoft.ReportingServices.Diagnostics.Weekly::get_WeeksInterval()
0xef2c  stloc.0
0xef2d  ldloca.s 0
0xef2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xef34  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0xef39  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xef3e  ldarg.0
0xef3f  ldarg.0
0xef40  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Weekly::get_DaysOfWeek()
0xef45  ldarg.1
0xef46  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteDaysElements(unsigned int32 days, class [System.Xml]System.Xml.XmlTextWriter writer)
0xef4b  ldarg.1
0xef4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xef51  ret
```
