# Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name

- ea: `0x1520`
- end: `0x154d`
- name: `Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1550`
- `0x1580`

## callees

- `0x1520`
- `0x1590`

## pseudocode

```c

```

## disassembly

```asm
0x1520  ldarg.0
0x1521  ldfld    bool Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_localized
0x1526  brtrue.s loc_1546
0x1528  ldarg.0
0x1529  ldc.i4.1
0x152a  stfld    bool Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_localized
0x152f  ldarg.0
0x1530  ldarg.0
0x1531  ldfld    string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_name
0x1536  callvirt instance string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::GetLocalizedString(string value)
0x153b  stloc.0
0x153c  ldloc.0
0x153d  brfalse.s loc_1546
0x153f  ldarg.0
0x1540  ldloc.0
0x1541  stfld    string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_name
0x1546  ldarg.0
0x1547  ldfld    string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::m_name
0x154c  ret
```
