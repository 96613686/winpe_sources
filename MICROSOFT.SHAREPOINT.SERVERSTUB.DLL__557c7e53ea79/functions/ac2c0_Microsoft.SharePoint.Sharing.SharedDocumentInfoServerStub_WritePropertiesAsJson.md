# Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::WritePropertiesAsJson

- ea: `0xac2c0`
- end: `0xac797`
- name: `Microsoft.SharePoint.Sharing.SharedDocumentInfoServerStub::WritePropertiesAsJson`
- size: `1239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xac2c0`

## string_xrefs

- `0xac46b`: `LinkingUrl`
- `0xac477`: `LinkingUrl`
- `0xac482`: `LinkingUrl`
- `0xac49a`: `LinkingUrl`
- `0xac383`: `Extension`
- `0xac38f`: `Extension`
- `0xac39a`: `Extension`
- `0xac3b2`: `Extension`
- `0xac723`: `UrlPath`
- `0xac72f`: `UrlPath`
- `0xac73a`: `UrlPath`
- `0xac752`: `UrlPath`

## pseudocode

```c

```

## disassembly

```asm
0xac2c0  ldarg.2
0xac2c1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo
0xac2c6  stloc.0
0xac2c7  ldloc.0
0xac2c8  brtrue.s loc_AC2CB
0xac2ca  ret
0xac2cb  ldarg.0
0xac2cc  ldarg.1
0xac2cd  ldarg.2
0xac2ce  ldarg.3
0xac2cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac2d4  ldarg.0
0xac2d5  ldstr    aAuthor_0// "Author"
0xac2da  ldarg.3
0xac2db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac2e0  ldarg.1
0xac2e1  ldstr    aAuthor_0// "Author"
0xac2e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac2eb  ldarg.3
0xac2ec  ldstr    aAuthor_0// "Author"
0xac2f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac2f6  ldarg.1
0xac2f7  ldloc.0
0xac2f8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Author()
0xac2fd  ldarg.3
0xac2fe  call     T0x2B000003
0xac303  ldarg.3
0xac304  ldstr    aAuthor_0// "Author"
0xac309  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac30e  ldarg.0
0xac30f  ldstr    aContenttypeid_0// "ContentTypeId"
0xac314  ldarg.3
0xac315  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac31a  ldarg.1
0xac31b  ldstr    aContenttypeid_0// "ContentTypeId"
0xac320  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac325  ldarg.3
0xac326  ldstr    aContenttypeid_0// "ContentTypeId"
0xac32b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac330  ldarg.1
0xac331  ldloc.0
0xac332  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ContentTypeId()
0xac337  ldarg.3
0xac338  call     T0x2B000156
0xac33d  ldarg.3
0xac33e  ldstr    aContenttypeid_0// "ContentTypeId"
0xac343  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac348  ldarg.0
0xac349  ldstr    aEditor// "Editor"
0xac34e  ldarg.3
0xac34f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac354  ldarg.1
0xac355  ldstr    aEditor// "Editor"
0xac35a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac35f  ldarg.3
0xac360  ldstr    aEditor// "Editor"
0xac365  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac36a  ldarg.1
0xac36b  ldloc.0
0xac36c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Editor()
0xac371  ldarg.3
0xac372  call     T0x2B000003
0xac377  ldarg.3
0xac378  ldstr    aEditor// "Editor"
0xac37d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac382  ldarg.0
0xac383  ldstr    aExtension_0// "Extension"
0xac388  ldarg.3
0xac389  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac38e  ldarg.1
0xac38f  ldstr    aExtension_0// "Extension"
0xac394  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac399  ldarg.3
0xac39a  ldstr    aExtension_0// "Extension"
0xac39f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac3a4  ldarg.1
0xac3a5  ldloc.0
0xac3a6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Extension()
0xac3ab  ldarg.3
0xac3ac  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac3b1  ldarg.3
0xac3b2  ldstr    aExtension_0// "Extension"
0xac3b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac3bc  ldarg.0
0xac3bd  ldstr    aFileleafref// "FileLeafRef"
0xac3c2  ldarg.3
0xac3c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac3c8  ldarg.1
0xac3c9  ldstr    aFileleafref// "FileLeafRef"
0xac3ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac3d3  ldarg.3
0xac3d4  ldstr    aFileleafref// "FileLeafRef"
0xac3d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac3de  ldarg.1
0xac3df  ldloc.0
0xac3e0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_FileLeafRef()
0xac3e5  ldarg.3
0xac3e6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac3eb  ldarg.3
0xac3ec  ldstr    aFileleafref// "FileLeafRef"
0xac3f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac3f6  ldarg.0
0xac3f7  ldstr    aFileref// "FileRef"
0xac3fc  ldarg.3
0xac3fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac402  ldarg.1
0xac403  ldstr    aFileref// "FileRef"
0xac408  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac40d  ldarg.3
0xac40e  ldstr    aFileref// "FileRef"
0xac413  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac418  ldarg.1
0xac419  ldloc.0
0xac41a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_FileRef()
0xac41f  ldarg.3
0xac420  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac425  ldarg.3
0xac426  ldstr    aFileref// "FileRef"
0xac42b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac430  ldarg.0
0xac431  ldstr    aIscontainer// "IsContainer"
0xac436  ldarg.3
0xac437  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac43c  ldarg.1
0xac43d  ldstr    aIscontainer// "IsContainer"
0xac442  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac447  ldarg.3
0xac448  ldstr    aIscontainer// "IsContainer"
0xac44d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac452  ldarg.1
0xac453  ldloc.0
0xac454  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_IsContainer()
0xac459  ldarg.3
0xac45a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac45f  ldarg.3
0xac460  ldstr    aIscontainer// "IsContainer"
0xac465  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac46a  ldarg.0
0xac46b  ldstr    aLinkingurl// "LinkingUrl"
0xac470  ldarg.3
0xac471  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac476  ldarg.1
0xac477  ldstr    aLinkingurl// "LinkingUrl"
0xac47c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac481  ldarg.3
0xac482  ldstr    aLinkingurl// "LinkingUrl"
0xac487  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac48c  ldarg.1
0xac48d  ldloc.0
0xac48e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_LinkingUrl()
0xac493  ldarg.3
0xac494  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac499  ldarg.3
0xac49a  ldstr    aLinkingurl// "LinkingUrl"
0xac49f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac4a4  ldarg.0
0xac4a5  ldstr    aListid_0// "ListId"
0xac4aa  ldarg.3
0xac4ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac4b0  ldarg.1
0xac4b1  ldstr    aListid_0// "ListId"
0xac4b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac4bb  ldarg.3
0xac4bc  ldstr    aListid_0// "ListId"
0xac4c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac4c6  ldarg.1
0xac4c7  ldloc.0
0xac4c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ListId()
0xac4cd  ldarg.3
0xac4ce  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac4d3  ldarg.3
0xac4d4  ldstr    aListid_0// "ListId"
0xac4d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac4de  ldarg.0
0xac4df  ldstr    aListitemid// "ListItemId"
0xac4e4  ldarg.3
0xac4e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac4ea  ldarg.1
0xac4eb  ldstr    aListitemid// "ListItemId"
0xac4f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac4f5  ldarg.3
0xac4f6  ldstr    aListitemid// "ListItemId"
0xac4fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac500  ldarg.1
0xac501  ldloc.0
0xac502  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ListItemId()
0xac507  ldarg.3
0xac508  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac50d  ldarg.3
0xac50e  ldstr    aListitemid// "ListItemId"
0xac513  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac518  ldarg.0
0xac519  ldstr    aModified// "Modified"
0xac51e  ldarg.3
0xac51f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac524  ldarg.1
0xac525  ldstr    aModified// "Modified"
0xac52a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac52f  ldarg.3
0xac530  ldstr    aModified// "Modified"
0xac535  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac53a  ldarg.1
0xac53b  ldloc.0
0xac53c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_Modified()
0xac541  ldarg.3
0xac542  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac547  ldarg.3
0xac548  ldstr    aModified// "Modified"
0xac54d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac552  ldarg.0
0xac553  ldstr    aProgid_1// "ProgId"
0xac558  ldarg.3
0xac559  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac55e  ldarg.1
0xac55f  ldstr    aProgid_1// "ProgId"
0xac564  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac569  ldarg.3
0xac56a  ldstr    aProgid_1// "ProgId"
0xac56f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac574  ldarg.1
0xac575  ldloc.0
0xac576  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ProgId()
0xac57b  ldarg.3
0xac57c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac581  ldarg.3
0xac582  ldstr    aProgid_1// "ProgId"
0xac587  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac58c  ldarg.0
0xac58d  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xac592  ldarg.3
0xac593  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac598  ldarg.1
0xac599  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xac59e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac5a3  ldarg.3
0xac5a4  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xac5a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac5ae  ldarg.1
0xac5af  ldloc.0
0xac5b0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ServerRedirectedEmbedUrl()
0xac5b5  ldarg.3
0xac5b6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac5bb  ldarg.3
0xac5bc  ldstr    aServerredirect_0// "ServerRedirectedEmbedUrl"
0xac5c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac5c6  ldarg.0
0xac5c7  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xac5cc  ldarg.3
0xac5cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac5d2  ldarg.1
0xac5d3  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xac5d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac5dd  ldarg.3
0xac5de  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xac5e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac5e8  ldarg.1
0xac5e9  ldloc.0
0xac5ea  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ServerRedirectedPreviewUrl()
0xac5ef  ldarg.3
0xac5f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac5f5  ldarg.3
0xac5f6  ldstr    aServerredirect_1// "ServerRedirectedPreviewUrl"
0xac5fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac600  ldarg.0
0xac601  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xac606  ldarg.3
0xac607  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac60c  ldarg.1
0xac60d  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xac612  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac617  ldarg.3
0xac618  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xac61d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac622  ldarg.1
0xac623  ldloc.0
0xac624  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_ServerRedirectedUrl()
0xac629  ldarg.3
0xac62a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac62f  ldarg.3
0xac630  ldstr    aServerredirect_2// "ServerRedirectedUrl"
0xac635  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac63a  ldarg.0
0xac63b  ldstr    aSiteid_0// "SiteId"
0xac640  ldarg.3
0xac641  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac646  ldarg.1
0xac647  ldstr    aSiteid_0// "SiteId"
0xac64c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xac651  ldarg.3
0xac652  ldstr    aSiteid_0// "SiteId"
0xac657  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xac65c  ldarg.1
0xac65d  ldloc.0
0xac65e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedDocumentInfo::get_SiteId()
0xac663  ldarg.3
0xac664  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xac669  ldarg.3
0xac66a  ldstr    aSiteid_0// "SiteId"
0xac66f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xac674  ldarg.0
  ... truncated ...
```
