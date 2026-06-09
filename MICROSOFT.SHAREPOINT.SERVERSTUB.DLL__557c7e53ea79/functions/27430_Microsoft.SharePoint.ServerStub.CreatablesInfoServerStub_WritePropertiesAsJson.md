# Microsoft.SharePoint.ServerStub.CreatablesInfoServerStub::WritePropertiesAsJson

- ea: `0x27430`
- end: `0x2752d`
- name: `Microsoft.SharePoint.ServerStub.CreatablesInfoServerStub::WritePropertiesAsJson`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x27430`

## string_xrefs

- `0x27445`: `CanCreateFolders`
- `0x27451`: `CanCreateFolders`
- `0x2745c`: `CanCreateFolders`
- `0x27474`: `CanCreateFolders`
- `0x2747f`: `CanCreateItems`
- `0x2748b`: `CanCreateItems`
- `0x27496`: `CanCreateItems`
- `0x274ae`: `CanCreateItems`

## pseudocode

```c

```

## disassembly

```asm
0x27430  ldarg.2
0x27431  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo
0x27436  stloc.0
0x27437  ldloc.0
0x27438  brtrue.s loc_2743B
0x2743a  ret
0x2743b  ldarg.0
0x2743c  ldarg.1
0x2743d  ldarg.2
0x2743e  ldarg.3
0x2743f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27444  ldarg.0
0x27445  ldstr    aCancreatefolde// "CanCreateFolders"
0x2744a  ldarg.3
0x2744b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27450  ldarg.1
0x27451  ldstr    aCancreatefolde// "CanCreateFolders"
0x27456  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2745b  ldarg.3
0x2745c  ldstr    aCancreatefolde// "CanCreateFolders"
0x27461  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x27466  ldarg.1
0x27467  ldloc.0
0x27468  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo::get_CanCreateFolders()
0x2746d  ldarg.3
0x2746e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x27473  ldarg.3
0x27474  ldstr    aCancreatefolde// "CanCreateFolders"
0x27479  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2747e  ldarg.0
0x2747f  ldstr    aCancreateitems// "CanCreateItems"
0x27484  ldarg.3
0x27485  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2748a  ldarg.1
0x2748b  ldstr    aCancreateitems// "CanCreateItems"
0x27490  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x27495  ldarg.3
0x27496  ldstr    aCancreateitems// "CanCreateItems"
0x2749b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x274a0  ldarg.1
0x274a1  ldloc.0
0x274a2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo::get_CanCreateItems()
0x274a7  ldarg.3
0x274a8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x274ad  ldarg.3
0x274ae  ldstr    aCancreateitems// "CanCreateItems"
0x274b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x274b8  ldarg.0
0x274b9  ldstr    aCanuploadfiles// "CanUploadFiles"
0x274be  ldarg.3
0x274bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x274c4  ldarg.1
0x274c5  ldstr    aCanuploadfiles// "CanUploadFiles"
0x274ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x274cf  ldarg.3
0x274d0  ldstr    aCanuploadfiles// "CanUploadFiles"
0x274d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x274da  ldarg.1
0x274db  ldloc.0
0x274dc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo::get_CanUploadFiles()
0x274e1  ldarg.3
0x274e2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x274e7  ldarg.3
0x274e8  ldstr    aCanuploadfiles// "CanUploadFiles"
0x274ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x274f2  ldarg.0
0x274f3  ldstr    aCreatablescoll// "CreatablesCollection"
0x274f8  ldarg.3
0x274f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x274fe  ldarg.1
0x274ff  ldstr    aCreatablescoll// "CreatablesCollection"
0x27504  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x27509  ldarg.3
0x2750a  ldstr    aCreatablescoll// "CreatablesCollection"
0x2750f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x27514  ldarg.1
0x27515  ldloc.0
0x27516  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo/CreatableItemInfoCollection [Microsoft.SharePoint]Microsoft.SharePoint.CreatablesInfo::get_CreatablesCollection()
0x2751b  ldarg.3
0x2751c  call     T0x2B000102
0x27521  ldarg.3
0x27522  ldstr    aCreatablescoll// "CreatablesCollection"
0x27527  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2752c  ret
```
