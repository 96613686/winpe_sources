# Microsoft.ReportingServices.Diagnostics.Monthly::ToXml

- ea: `0xf030`
- end: `0xf06a`
- name: `Microsoft.ReportingServices.Diagnostics.Monthly::ToXml`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xe7e0`
- `0xeb60`
- `0xefd0`
- `0xeff0`
- `0xf090`

## pseudocode

```c

```

## disassembly

```asm
0xf030  ldarg.1
0xf031  ldstr    aMonthlyrecurre// "MonthlyRecurrence"
0xf036  call     string Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace()
0xf03b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xf040  ldarg.1
0xf041  ldstr    aDays// "Days"
0xf046  ldarg.0
0xf047  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Monthly::get_DaysOfMonth()
0xf04c  call     string Microsoft.ReportingServices.Diagnostics.Monthly::GetDayRange(unsigned int32 dayBitMap)
0xf051  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xf056  ldarg.0
0xf057  ldarg.0
0xf058  call     instance unsigned int32 Microsoft.ReportingServices.Diagnostics.Monthly::get_Months()
0xf05d  ldarg.1
0xf05e  call     instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteMonthsElements(unsigned int32 months, class [System.Xml]System.Xml.XmlTextWriter writer)
0xf063  ldarg.1
0xf064  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf069  ret
```
