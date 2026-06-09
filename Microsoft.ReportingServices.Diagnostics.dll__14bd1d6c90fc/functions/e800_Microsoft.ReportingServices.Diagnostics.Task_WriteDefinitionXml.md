# Microsoft.ReportingServices.Diagnostics.Task::WriteDefinitionXml

- ea: `0xe800`
- end: `0xe8c7`
- name: `Microsoft.ReportingServices.Diagnostics.Task::WriteDefinitionXml`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe770`
- `0xe8d0`

## callees

- `0xac70`
- `0xd830`
- `0xe7e0`
- `0xe800`
- `0xea00`
- `0xea90`
- `0xf370`
- `0xf390`
- `0xf3e0`

## string_xrefs

- `0xe801`: `ScheduleDefinition`
- `0xe80c`: `xmlns`
- `0xe822`: `xmlns`
- `0xe817`: `http://www.w3.org/2001/XMLSchema`
- `0xe82d`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xe800  ldarg.1
0xe801  ldstr    aScheduledefini// "ScheduleDefinition"
0xe806  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xe80b  ldarg.1
0xe80c  ldstr    aXmlns// "xmlns"
0xe811  ldstr    aXsd// "xsd"
0xe816  ldnull
0xe817  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xe81c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xe821  ldarg.1
0xe822  ldstr    aXmlns// "xmlns"
0xe827  ldstr    aXsi// "xsi"
0xe82c  ldnull
0xe82d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xe832  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xe837  ldarg.1
0xe838  ldstr    aStartdatetime// "StartDateTime"
0xe83d  call     string Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace()
0xe842  ldarg.0
0xe843  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe848  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xe84d  call     string Microsoft.ReportingServices.Diagnostics.Globals::ToPublicDateTimeFormat(valuetype [mscorlib]System.DateTime date)
0xe852  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0xe857  ldarg.0
0xe858  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe85d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xe862  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xe867  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe86c  brfalse.s loc_E89B
0xe86e  ldarg.1
0xe86f  ldstr    aEnddate// "EndDate"
0xe874  call     string Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace()
0xe879  ldarg.0
0xe87a  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe87f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xe884  stloc.0
0xe885  ldloca.s 0
0xe887  ldstr    aYyyyMmDd// "yyyy-MM-dd"
0xe88c  call     class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.DateTimeFormatInfo::get_InvariantInfo()
0xe891  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xe896  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string, string)
0xe89b  ldarg.0
0xe89c  ldarg.1
0xe89d  call     instance void Microsoft.ReportingServices.Diagnostics.Task::WriteFlagXml(class [System.Xml]System.Xml.XmlTextWriter writer)
0xe8a2  ldarg.0
0xe8a3  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe8a8  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xe8ad  brfalse.s loc_E8C0
0xe8af  ldarg.0
0xe8b0  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe8b5  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xe8ba  ldarg.1
0xe8bb  callvirt instance void Microsoft.ReportingServices.Diagnostics.BaseTriggerData::ToXml(class [System.Xml]System.Xml.XmlTextWriter writer)
0xe8c0  ldarg.1
0xe8c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xe8c6  ret
```
