# Microsoft.SharePoint.Publishing.AddinSettingsServerStub::WritePropertiesAsJson

- ea: `0x1250`
- end: `0x146f`
- name: `Microsoft.SharePoint.Publishing.AddinSettingsServerStub::WritePropertiesAsJson`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1250`

## pseudocode

```c

```

## disassembly

```asm
0x1250  ldarg.2
0x1251  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings
0x1256  stloc.0
0x1257  ldloc.0
0x1258  brtrue.s loc_125B
0x125a  ret
0x125b  ldarg.0
0x125c  ldarg.1
0x125d  ldarg.2
0x125e  ldarg.3
0x125f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1264  ldarg.0
0x1265  ldstr    aDescription// "Description"
0x126a  ldarg.3
0x126b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1270  ldarg.1
0x1271  ldstr    aDescription// "Description"
0x1276  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x127b  ldarg.3
0x127c  ldstr    aDescription// "Description"
0x1281  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1286  ldarg.1
0x1287  ldloc.0
0x1288  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Description()
0x128d  ldarg.3
0x128e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1293  ldarg.3
0x1294  ldstr    aDescription// "Description"
0x1299  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x129e  ldarg.0
0x129f  ldstr    aEnabled// "Enabled"
0x12a4  ldarg.3
0x12a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12aa  ldarg.1
0x12ab  ldstr    aEnabled// "Enabled"
0x12b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x12b5  ldarg.3
0x12b6  ldstr    aEnabled// "Enabled"
0x12bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x12c0  ldarg.1
0x12c1  ldloc.0
0x12c2  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Enabled()
0x12c7  ldarg.3
0x12c8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12cd  ldarg.3
0x12ce  ldstr    aEnabled// "Enabled"
0x12d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x12d8  ldarg.0
0x12d9  ldstr    aHeadscript// "HeadScript"
0x12de  ldarg.3
0x12df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12e4  ldarg.1
0x12e5  ldstr    aHeadscript// "HeadScript"
0x12ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x12ef  ldarg.3
0x12f0  ldstr    aHeadscript// "HeadScript"
0x12f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x12fa  ldarg.1
0x12fb  ldloc.0
0x12fc  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HeadScript()
0x1301  ldarg.3
0x1302  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1307  ldarg.3
0x1308  ldstr    aHeadscript// "HeadScript"
0x130d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1312  ldarg.0
0x1313  ldstr    aHtmlendbody// "HtmlEndBody"
0x1318  ldarg.3
0x1319  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x131e  ldarg.1
0x131f  ldstr    aHtmlendbody// "HtmlEndBody"
0x1324  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1329  ldarg.3
0x132a  ldstr    aHtmlendbody// "HtmlEndBody"
0x132f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1334  ldarg.1
0x1335  ldloc.0
0x1336  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HtmlEndBody()
0x133b  ldarg.3
0x133c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1341  ldarg.3
0x1342  ldstr    aHtmlendbody// "HtmlEndBody"
0x1347  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x134c  ldarg.0
0x134d  ldstr    aHtmlstartbody// "HtmlStartBody"
0x1352  ldarg.3
0x1353  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1358  ldarg.1
0x1359  ldstr    aHtmlstartbody// "HtmlStartBody"
0x135e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1363  ldarg.3
0x1364  ldstr    aHtmlstartbody// "HtmlStartBody"
0x1369  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x136e  ldarg.1
0x136f  ldloc.0
0x1370  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_HtmlStartBody()
0x1375  ldarg.3
0x1376  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x137b  ldarg.3
0x137c  ldstr    aHtmlstartbody// "HtmlStartBody"
0x1381  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1386  ldarg.0
0x1387  ldstr    aId// "Id"
0x138c  ldarg.3
0x138d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1392  ldarg.1
0x1393  ldstr    aId// "Id"
0x1398  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x139d  ldarg.3
0x139e  ldstr    aId// "Id"
0x13a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x13a8  ldarg.1
0x13a9  ldloc.0
0x13aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Id()
0x13af  ldarg.3
0x13b0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13b5  ldarg.3
0x13b6  ldstr    aId// "Id"
0x13bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13c0  ldarg.0
0x13c1  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0x13c6  ldarg.3
0x13c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13cc  ldarg.1
0x13cd  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0x13d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x13d7  ldarg.3
0x13d8  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0x13dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x13e2  ldarg.1
0x13e3  ldloc.0
0x13e4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_MetaTagPagePropertyMappings()
0x13e9  ldarg.3
0x13ea  call     T0x2B000005
0x13ef  ldarg.3
0x13f0  ldstr    aMetatagpagepro// "MetaTagPagePropertyMappings"
0x13f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x13fa  ldarg.0
0x13fb  ldstr    aNamespace// "Namespace"
0x1400  ldarg.3
0x1401  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1406  ldarg.1
0x1407  ldstr    aNamespace// "Namespace"
0x140c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1411  ldarg.3
0x1412  ldstr    aNamespace// "Namespace"
0x1417  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x141c  ldarg.1
0x141d  ldloc.0
0x141e  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Namespace()
0x1423  ldarg.3
0x1424  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1429  ldarg.3
0x142a  ldstr    aNamespace// "Namespace"
0x142f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x1434  ldarg.0
0x1435  ldstr    aTitle// "Title"
0x143a  ldarg.3
0x143b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1440  ldarg.1
0x1441  ldstr    aTitle// "Title"
0x1446  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x144b  ldarg.3
0x144c  ldstr    aTitle// "Title"
0x1451  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x1456  ldarg.1
0x1457  ldloc.0
0x1458  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings::get_Title()
0x145d  ldarg.3
0x145e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1463  ldarg.3
0x1464  ldstr    aTitle// "Title"
0x1469  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x146e  ret
```
