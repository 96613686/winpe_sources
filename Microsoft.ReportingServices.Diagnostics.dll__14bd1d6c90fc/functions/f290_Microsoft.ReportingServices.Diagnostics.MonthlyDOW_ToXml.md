# Microsoft.ReportingServices.Diagnostics.MonthlyDOW::ToXml

- ea: `0xf290`
- end: `0xf2ce`
- name: `Microsoft.ReportingServices.Diagnostics.MonthlyDOW::ToXml`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xe7e0`
- `0xeaa0`
- `0xeb60`
- `0xecb0`
- `0xf210`
- `0xf230`
- `0xf250`

## pseudocode

```c

```

## disassembly

```asm
0xf290  ldarg.1
0xf291  ldstr    aMonthlydowrecu// "MonthlyDOWRecurrence"
0xf296  call     string Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace()
0xf29b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xf2a0  ldarg.0
0xf2a1  ldarg.0
0xf2a2  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Week()
0xf2a7  ldarg.1
0xf2a8  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteWeeksOfMonth(unsigned int32 weeks, class [System.Xml]System.Xml.XmlTextWriter writer)
0xf2ad  ldarg.0
0xf2ae  ldarg.0
0xf2af  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_DaysOfWeek()
0xf2b4  ldarg.1
0xf2b5  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteDaysElements(unsigned int32 days, class [System.Xml]System.Xml.XmlTextWriter writer)
0xf2ba  ldarg.0
0xf2bb  ldarg.0
0xf2bc  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.MonthlyDOW::get_Months()
0xf2c1  ldarg.1
0xf2c2  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteMonthsElements(unsigned int32 months, class [System.Xml]System.Xml.XmlTextWriter writer)
0xf2c7  ldarg.1
0xf2c8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf2cd  ret
```
