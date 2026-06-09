# Microsoft.SharePoint.Publishing.VariationLabelServerStub::WritePropertiesAsJson

- ea: `0x130d0`
- end: `0x13241`
- name: `Microsoft.SharePoint.Publishing.VariationLabelServerStub::WritePropertiesAsJson`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x130d0`

## pseudocode

```c

```

## disassembly

```asm
0x130d0  ldarg.2
0x130d1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel
0x130d6  stloc.0
0x130d7  ldloc.0
0x130d8  brtrue.s loc_130DB
0x130da  ret
0x130db  ldarg.0
0x130dc  ldarg.1
0x130dd  ldarg.2
0x130de  ldarg.3
0x130df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x130e4  ldarg.0
0x130e5  ldstr    aDisplayname// "DisplayName"
0x130ea  ldarg.3
0x130eb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x130f0  ldarg.1
0x130f1  ldstr    aDisplayname// "DisplayName"
0x130f6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x130fb  ldarg.3
0x130fc  ldstr    aDisplayname// "DisplayName"
0x13101  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x13106  ldarg.1
0x13107  ldloc.0
0x13108  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_DisplayName()
0x1310d  ldarg.3
0x1310e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13113  ldarg.3
0x13114  ldstr    aDisplayname// "DisplayName"
0x13119  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1311e  ldarg.0
0x1311f  ldstr    aIssource// "IsSource"
0x13124  ldarg.3
0x13125  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1312a  ldarg.1
0x1312b  ldstr    aIssource// "IsSource"
0x13130  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x13135  ldarg.3
0x13136  ldstr    aIssource// "IsSource"
0x1313b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x13140  ldarg.1
0x13141  ldloc.0
0x13142  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_IsSource()
0x13147  ldarg.3
0x13148  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1314d  ldarg.3
0x1314e  ldstr    aIssource// "IsSource"
0x13153  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13158  ldarg.0
0x13159  ldstr    aLanguage// "Language"
0x1315e  ldarg.3
0x1315f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13164  ldarg.1
0x13165  ldstr    aLanguage// "Language"
0x1316a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1316f  ldarg.3
0x13170  ldstr    aLanguage// "Language"
0x13175  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1317a  ldarg.1
0x1317b  ldloc.0
0x1317c  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Language()
0x13181  ldarg.3
0x13182  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13187  ldarg.3
0x13188  ldstr    aLanguage// "Language"
0x1318d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13192  ldarg.0
0x13193  ldstr    aLocale// "Locale"
0x13198  ldarg.3
0x13199  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1319e  ldarg.1
0x1319f  ldstr    aLocale// "Locale"
0x131a4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x131a9  ldarg.3
0x131aa  ldstr    aLocale// "Locale"
0x131af  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x131b4  ldarg.1
0x131b5  ldloc.0
0x131b6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Locale()
0x131bb  ldarg.3
0x131bc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x131c1  ldarg.3
0x131c2  ldstr    aLocale// "Locale"
0x131c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x131cc  ldarg.0
0x131cd  ldstr    aTitle// "Title"
0x131d2  ldarg.3
0x131d3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x131d8  ldarg.1
0x131d9  ldstr    aTitle// "Title"
0x131de  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x131e3  ldarg.3
0x131e4  ldstr    aTitle// "Title"
0x131e9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x131ee  ldarg.1
0x131ef  ldloc.0
0x131f0  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_Title()
0x131f5  ldarg.3
0x131f6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x131fb  ldarg.3
0x131fc  ldstr    aTitle// "Title"
0x13201  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13206  ldarg.0
0x13207  ldstr    aTopweburl// "TopWebUrl"
0x1320c  ldarg.3
0x1320d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13212  ldarg.1
0x13213  ldstr    aTopweburl// "TopWebUrl"
0x13218  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1321d  ldarg.3
0x1321e  ldstr    aTopweburl// "TopWebUrl"
0x13223  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x13228  ldarg.1
0x13229  ldloc.0
0x1322a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel::get_TopWebUrl()
0x1322f  ldarg.3
0x13230  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13235  ldarg.3
0x13236  ldstr    aTopweburl// "TopWebUrl"
0x1323b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13240  ret
```
