# Microsoft.Reporting.WebForms.ReportControl::GetDeviceInfoBlackList

- ea: `0x10df0`
- end: `0x10ecd`
- name: `Microsoft.Reporting.WebForms.ReportControl::GetDeviceInfoBlackList`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x12cf0`

## callees

- `0x26e0`
- `0x26f0`
- `0x2770`
- `0x10df0`
- `0x24f60`
- `0x24f70`
- `0x24f80`

## string_xrefs

- `0x10e7c`: `ReplacementRoot`
- `0x10ea9`: `LinkTarget`

## pseudocode

```c

```

## disassembly

```asm
0x10df0  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10df5  brtrue   loc_10EC7
0x10dfa  newobj   instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::.ctor()
0x10dff  stsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e04  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e09  ldstr    aHtmlfragment// "HTMLFragment"
0x10e0e  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e13  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e18  ldstr    aSection// "Section"
0x10e1d  call     string Microsoft.Reporting.WebForms.Errors::get_InvalidDeviceInfoSection()
0x10e22  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName, string deviceInfoExceptionText)
0x10e27  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e2c  ldstr    aStreamroot// "StreamRoot"
0x10e31  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e36  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e3b  ldstr    aResourcestream_0// "ResourceStreamRoot"
0x10e40  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e45  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e4a  ldstr    aActionscript// "ActionScript"
0x10e4f  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e54  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e59  ldstr    aJavascript_1// "JavaScript"
0x10e5e  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e63  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e68  ldstr    aFindstring// "FindString"
0x10e6d  call     string Microsoft.Reporting.WebForms.Errors::get_InvalidDeviceInfoFind()
0x10e72  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName, string deviceInfoExceptionText)
0x10e77  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e7c  ldstr    aReplacementroo// "ReplacementRoot"
0x10e81  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e86  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e8b  ldstr    aPrefixid// "PrefixId"
0x10e90  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10e95  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10e9a  ldstr    aStylestream// "StyleStream"
0x10e9f  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10ea4  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10ea9  ldstr    aLinktarget// "LinkTarget"
0x10eae  call     string Microsoft.Reporting.WebForms.Errors::get_InvalidDeviceInfoLinkTarget()
0x10eb3  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName, string deviceInfoExceptionText)
0x10eb8  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10ebd  ldstr    aExpandcontent// "ExpandContent"
0x10ec2  callvirt instance void Microsoft.Reporting.WebForms.DeviceInfoNameBlackList::Add(string deviceInfoName)
0x10ec7  ldsfld   class Microsoft.Reporting.WebForms.DeviceInfoNameBlackList Microsoft.Reporting.WebForms.ReportControl::m_blackListDeviceInfoNames
0x10ecc  ret
```
