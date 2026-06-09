# Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteMonthsElements

- ea: `0xeb60`
- end: `0xeca8`
- name: `Microsoft.ReportingServices.Diagnostics.BaseTriggerData::WriteMonthsElements`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf030`
- `0xf290`

## callees

- `0xeb60`

## pseudocode

```c

```

## disassembly

```asm
0xeb60  ldarg.1
0xeb61  ldarg.2
0xeb62  ldstr    aMonthsofyear// "MonthsOfYear"
0xeb67  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xeb6c  dup
0xeb6d  ldc.i4.1
0xeb6e  and
0xeb6f  ldc.i4.1
0xeb70  bne.un.s loc_EB82
0xeb72  ldarg.2
0xeb73  ldstr    aJanuary// "January"
0xeb78  ldstr    aTrue_0// "true"
0xeb7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb82  dup
0xeb83  ldc.i4.2
0xeb84  and
0xeb85  ldc.i4.2
0xeb86  bne.un.s loc_EB98
0xeb88  ldarg.2
0xeb89  ldstr    aFebruary// "February"
0xeb8e  ldstr    aTrue_0// "true"
0xeb93  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeb98  dup
0xeb99  ldc.i4.4
0xeb9a  and
0xeb9b  ldc.i4.4
0xeb9c  bne.un.s loc_EBAE
0xeb9e  ldarg.2
0xeb9f  ldstr    aMarch// "March"
0xeba4  ldstr    aTrue_0// "true"
0xeba9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xebae  dup
0xebaf  ldc.i4.8
0xebb0  and
0xebb1  ldc.i4.8
0xebb2  bne.un.s loc_EBC4
0xebb4  ldarg.2
0xebb5  ldstr    aApril// "April"
0xebba  ldstr    aTrue_0// "true"
0xebbf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xebc4  dup
0xebc5  ldc.i4.s 0x10
0xebc7  and
0xebc8  ldc.i4.s 0x10
0xebca  bne.un.s loc_EBDC
0xebcc  ldarg.2
0xebcd  ldstr    aMay// "May"
0xebd2  ldstr    aTrue_0// "true"
0xebd7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xebdc  dup
0xebdd  ldc.i4.s 0x20
0xebdf  and
0xebe0  ldc.i4.s 0x20
0xebe2  bne.un.s loc_EBF4
0xebe4  ldarg.2
0xebe5  ldstr    aJune// "June"
0xebea  ldstr    aTrue_0// "true"
0xebef  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xebf4  dup
0xebf5  ldc.i4.s 0x40
0xebf7  and
0xebf8  ldc.i4.s 0x40
0xebfa  bne.un.s loc_EC0C
0xebfc  ldarg.2
0xebfd  ldstr    aJuly// "July"
0xec02  ldstr    aTrue_0// "true"
0xec07  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xec0c  dup
0xec0d  ldc.i4   0x80
0xec12  and
0xec13  ldc.i4   0x80
0xec18  bne.un.s loc_EC2A
0xec1a  ldarg.2
0xec1b  ldstr    aAugust// "August"
0xec20  ldstr    aTrue_0// "true"
0xec25  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xec2a  dup
0xec2b  ldc.i4   0x100
0xec30  and
0xec31  ldc.i4   0x100
0xec36  bne.un.s loc_EC48
0xec38  ldarg.2
0xec39  ldstr    aSeptember// "September"
0xec3e  ldstr    aTrue_0// "true"
0xec43  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xec48  dup
0xec49  ldc.i4   0x200
0xec4e  and
0xec4f  ldc.i4   0x200
0xec54  bne.un.s loc_EC66
0xec56  ldarg.2
0xec57  ldstr    aOctober// "October"
0xec5c  ldstr    aTrue_0// "true"
0xec61  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xec66  dup
0xec67  ldc.i4   0x400
0xec6c  and
0xec6d  ldc.i4   0x400
0xec72  bne.un.s loc_EC84
0xec74  ldarg.2
0xec75  ldstr    aNovember// "November"
0xec7a  ldstr    aTrue_0// "true"
0xec7f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xec84  ldc.i4   0x800
0xec89  and
0xec8a  ldc.i4   0x800
0xec8f  bne.un.s loc_ECA1
0xec91  ldarg.2
0xec92  ldstr    aDecember// "December"
0xec97  ldstr    aTrue_0// "true"
0xec9c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xeca1  ldarg.2
0xeca2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xeca7  ret
```
