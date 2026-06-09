# Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteDaysElements

- ea: `0xeaa0`
- end: `0xeb52`
- name: `Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteDaysElements`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xef10`
- `0xf290`

## callees

- `0xeaa0`

## pseudocode

```c

```

## disassembly

```asm
0xeaa0  ldarg.1
0xeaa1  ldarg.2
0xeaa2  ldstr    aDaysofweek// "DaysOfWeek"
0xeaa7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xeaac  dup
0xeaad  ldc.i4.1
0xeaae  and
0xeaaf  ldc.i4.1
0xeab0  bne.un.s loc_EAC2
0xeab2  ldarg.2
0xeab3  ldstr    aSunday// "Sunday"
0xeab8  ldstr    aTrue_0// "true"
0xeabd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeac2  dup
0xeac3  ldc.i4.2
0xeac4  and
0xeac5  ldc.i4.2
0xeac6  bne.un.s loc_EAD8
0xeac8  ldarg.2
0xeac9  ldstr    aMonday// "Monday"
0xeace  ldstr    aTrue_0// "true"
0xead3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xead8  dup
0xead9  ldc.i4.4
0xeada  and
0xeadb  ldc.i4.4
0xeadc  bne.un.s loc_EAEE
0xeade  ldarg.2
0xeadf  ldstr    aTuesday// "Tuesday"
0xeae4  ldstr    aTrue_0// "true"
0xeae9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeaee  dup
0xeaef  ldc.i4.8
0xeaf0  and
0xeaf1  ldc.i4.8
0xeaf2  bne.un.s loc_EB04
0xeaf4  ldarg.2
0xeaf5  ldstr    aWednesday// "Wednesday"
0xeafa  ldstr    aTrue_0// "true"
0xeaff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb04  dup
0xeb05  ldc.i4.s 0x10
0xeb07  and
0xeb08  ldc.i4.s 0x10
0xeb0a  bne.un.s loc_EB1C
0xeb0c  ldarg.2
0xeb0d  ldstr    aThursday// "Thursday"
0xeb12  ldstr    aTrue_0// "true"
0xeb17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb1c  dup
0xeb1d  ldc.i4.s 0x20
0xeb1f  and
0xeb20  ldc.i4.s 0x20
0xeb22  bne.un.s loc_EB34
0xeb24  ldarg.2
0xeb25  ldstr    aFriday// "Friday"
0xeb2a  ldstr    aTrue_0// "true"
0xeb2f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb34  ldc.i4.s 0x40
0xeb36  and
0xeb37  ldc.i4.s 0x40
0xeb39  bne.un.s loc_EB4B
0xeb3b  ldarg.2
0xeb3c  ldstr    aSaturday// "Saturday"
0xeb41  ldstr    aTrue_0// "true"
0xeb46  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb4b  ldarg.2
0xeb4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xeb51  ret
```
