# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::WritePropertiesAsJson

- ea: `0xa4b0`
- end: `0xa539`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::WritePropertiesAsJson`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa4b0`

## string_xrefs

- `0xa4ff`: `CreateFriendlyUrlsForNewPages`
- `0xa50b`: `CreateFriendlyUrlsForNewPages`
- `0xa516`: `CreateFriendlyUrlsForNewPages`
- `0xa52e`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa4b0  ldarg.2
0xa4b1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa4b6  stloc.0
0xa4b7  ldloc.0
0xa4b8  brtrue.s loc_A4BB
0xa4ba  ret
0xa4bb  ldarg.0
0xa4bc  ldarg.1
0xa4bd  ldarg.2
0xa4be  ldarg.3
0xa4bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4c4  ldarg.0
0xa4c5  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa4ca  ldarg.3
0xa4cb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4d0  ldarg.1
0xa4d1  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa4d6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa4db  ldarg.3
0xa4dc  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa4e1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa4e6  ldarg.1
0xa4e7  ldloc.0
0xa4e8  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_AddNewPagesToNavigation()
0xa4ed  ldarg.3
0xa4ee  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa4f3  ldarg.3
0xa4f4  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa4f9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa4fe  ldarg.0
0xa4ff  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa504  ldarg.3
0xa505  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa50a  ldarg.1
0xa50b  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa510  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xa515  ldarg.3
0xa516  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa51b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xa520  ldarg.1
0xa521  ldloc.0
0xa522  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_CreateFriendlyUrlsForNewPages()
0xa527  ldarg.3
0xa528  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa52d  ldarg.3
0xa52e  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa533  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xa538  ret
```
