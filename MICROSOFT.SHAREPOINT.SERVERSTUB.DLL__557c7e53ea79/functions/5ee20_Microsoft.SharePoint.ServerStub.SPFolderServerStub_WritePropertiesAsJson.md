# Microsoft.SharePoint.ServerStub.SPFolderServerStub::WritePropertiesAsJson

- ea: `0x5ee20`
- end: `0x5f079`
- name: `Microsoft.SharePoint.ServerStub.SPFolderServerStub::WritePropertiesAsJson`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5ee20`

## string_xrefs

- `0x5ef91`: `TimeCreated`
- `0x5ef9d`: `TimeCreated`
- `0x5efa8`: `TimeCreated`
- `0x5efc0`: `TimeCreated`
- `0x5f03f`: `WelcomePage`
- `0x5f04b`: `WelcomePage`
- `0x5f056`: `WelcomePage`
- `0x5f06e`: `WelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0x5ee20  ldarg.2
0x5ee21  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x5ee26  stloc.0
0x5ee27  ldloc.0
0x5ee28  brtrue.s loc_5EE2B
0x5ee2a  ret
0x5ee2b  ldarg.0
0x5ee2c  ldarg.1
0x5ee2d  ldarg.2
0x5ee2e  ldarg.3
0x5ee2f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ee34  ldarg.0
0x5ee35  ldstr    aExists// "Exists"
0x5ee3a  ldarg.3
0x5ee3b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ee40  ldarg.1
0x5ee41  ldstr    aExists// "Exists"
0x5ee46  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5ee4b  ldarg.3
0x5ee4c  ldstr    aExists// "Exists"
0x5ee51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5ee56  ldarg.1
0x5ee57  ldloc.0
0x5ee58  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Exists()
0x5ee5d  ldarg.3
0x5ee5e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ee63  ldarg.3
0x5ee64  ldstr    aExists// "Exists"
0x5ee69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5ee6e  ldarg.0
0x5ee6f  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5ee74  ldarg.3
0x5ee75  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ee7a  ldarg.1
0x5ee7b  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5ee80  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5ee85  ldarg.3
0x5ee86  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5ee8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5ee90  ldarg.1
0x5ee91  ldloc.0
0x5ee92  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_IsWOPIEnabled()
0x5ee97  ldarg.3
0x5ee98  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ee9d  ldarg.3
0x5ee9e  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5eea3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5eea8  ldarg.0
0x5eea9  ldstr    aItemcount// "ItemCount"
0x5eeae  ldarg.3
0x5eeaf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5eeb4  ldarg.1
0x5eeb5  ldstr    aItemcount// "ItemCount"
0x5eeba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5eebf  ldarg.3
0x5eec0  ldstr    aItemcount// "ItemCount"
0x5eec5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5eeca  ldarg.1
0x5eecb  ldloc.0
0x5eecc  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ItemCount()
0x5eed1  ldarg.3
0x5eed2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5eed7  ldarg.3
0x5eed8  ldstr    aItemcount// "ItemCount"
0x5eedd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5eee2  ldarg.0
0x5eee3  ldstr    aName// "Name"
0x5eee8  ldarg.3
0x5eee9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5eeee  ldarg.1
0x5eeef  ldstr    aName// "Name"
0x5eef4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5eef9  ldarg.3
0x5eefa  ldstr    aName// "Name"
0x5eeff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5ef04  ldarg.1
0x5ef05  ldloc.0
0x5ef06  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Name()
0x5ef0b  ldarg.3
0x5ef0c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef11  ldarg.3
0x5ef12  ldstr    aName// "Name"
0x5ef17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5ef1c  ldarg.0
0x5ef1d  ldstr    aProgid// "ProgID"
0x5ef22  ldarg.3
0x5ef23  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef28  ldarg.1
0x5ef29  ldstr    aProgid// "ProgID"
0x5ef2e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5ef33  ldarg.3
0x5ef34  ldstr    aProgid// "ProgID"
0x5ef39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5ef3e  ldarg.1
0x5ef3f  ldloc.0
0x5ef40  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ProgID()
0x5ef45  ldarg.3
0x5ef46  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef4b  ldarg.3
0x5ef4c  ldstr    aProgid// "ProgID"
0x5ef51  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5ef56  ldarg.0
0x5ef57  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5ef5c  ldarg.3
0x5ef5d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef62  ldarg.1
0x5ef63  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5ef68  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5ef6d  ldarg.3
0x5ef6e  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5ef73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5ef78  ldarg.1
0x5ef79  ldloc.0
0x5ef7a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ServerRelativeUrl()
0x5ef7f  ldarg.3
0x5ef80  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef85  ldarg.3
0x5ef86  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5ef8b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5ef90  ldarg.0
0x5ef91  ldstr    aTimecreated// "TimeCreated"
0x5ef96  ldarg.3
0x5ef97  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ef9c  ldarg.1
0x5ef9d  ldstr    aTimecreated// "TimeCreated"
0x5efa2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5efa7  ldarg.3
0x5efa8  ldstr    aTimecreated// "TimeCreated"
0x5efad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5efb2  ldarg.1
0x5efb3  ldloc.0
0x5efb4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_TimeCreated()
0x5efb9  ldarg.3
0x5efba  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5efbf  ldarg.3
0x5efc0  ldstr    aTimecreated// "TimeCreated"
0x5efc5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5efca  ldarg.0
0x5efcb  ldstr    aTimelastmodifi// "TimeLastModified"
0x5efd0  ldarg.3
0x5efd1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5efd6  ldarg.1
0x5efd7  ldstr    aTimelastmodifi// "TimeLastModified"
0x5efdc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5efe1  ldarg.3
0x5efe2  ldstr    aTimelastmodifi// "TimeLastModified"
0x5efe7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5efec  ldarg.1
0x5efed  ldloc.0
0x5efee  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_TimeLastModified()
0x5eff3  ldarg.3
0x5eff4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5eff9  ldarg.3
0x5effa  ldstr    aTimelastmodifi// "TimeLastModified"
0x5efff  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5f004  ldarg.0
0x5f005  ldstr    aUniqueid_0// "UniqueId"
0x5f00a  ldarg.3
0x5f00b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f010  ldarg.1
0x5f011  ldstr    aUniqueid_0// "UniqueId"
0x5f016  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5f01b  ldarg.3
0x5f01c  ldstr    aUniqueid_0// "UniqueId"
0x5f021  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5f026  ldarg.1
0x5f027  ldloc.0
0x5f028  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_UniqueId()
0x5f02d  ldarg.3
0x5f02e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f033  ldarg.3
0x5f034  ldstr    aUniqueid_0// "UniqueId"
0x5f039  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5f03e  ldarg.0
0x5f03f  ldstr    aWelcomepage// "WelcomePage"
0x5f044  ldarg.3
0x5f045  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f04a  ldarg.1
0x5f04b  ldstr    aWelcomepage// "WelcomePage"
0x5f050  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x5f055  ldarg.3
0x5f056  ldstr    aWelcomepage// "WelcomePage"
0x5f05b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x5f060  ldarg.1
0x5f061  ldloc.0
0x5f062  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_WelcomePage()
0x5f067  ldarg.3
0x5f068  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f06d  ldarg.3
0x5f06e  ldstr    aWelcomepage// "WelcomePage"
0x5f073  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x5f078  ret
```
