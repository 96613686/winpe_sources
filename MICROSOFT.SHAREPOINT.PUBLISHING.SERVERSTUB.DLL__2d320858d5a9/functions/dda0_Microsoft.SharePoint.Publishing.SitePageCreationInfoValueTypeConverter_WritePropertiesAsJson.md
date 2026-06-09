# Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::WritePropertiesAsJson

- ea: `0xdda0`
- end: `0xde8d`
- name: `Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::WritePropertiesAsJson`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdda0`

## string_xrefs

- `0xde75`: `WebRelativeFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xdda0  ldarg.2
0xdda1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo
0xdda6  stloc.0
0xdda7  ldloc.0
0xdda8  brtrue.s loc_DDAB
0xddaa  ret
0xddab  ldarg.0
0xddac  ldarg.1
0xddad  ldarg.2
0xddae  ldarg.3
0xddaf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xddb4  ldarg.1
0xddb5  ldstr    aCanvascontent1// "CanvasContent1"
0xddba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xddbf  ldarg.1
0xddc0  ldloc.0
0xddc1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_CanvasContent1()
0xddc6  ldarg.3
0xddc7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xddcc  ldarg.1
0xddcd  ldstr    aContenttypeid// "ContentTypeId"
0xddd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xddd7  ldarg.1
0xddd8  ldloc.0
0xddd9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_ContentTypeId()
0xddde  ldarg.3
0xdddf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdde4  ldarg.1
0xdde5  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xddea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xddef  ldarg.1
0xddf0  ldloc.0
0xddf1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_LayoutWebpartsContent()
0xddf6  ldarg.3
0xddf7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xddfc  ldarg.1
0xddfd  ldstr    aName// "Name"
0xde02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde07  ldarg.1
0xde08  ldloc.0
0xde09  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_Name()
0xde0e  ldarg.3
0xde0f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xde14  ldarg.1
0xde15  ldstr    aPagelayouttype// "PageLayoutType"
0xde1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde1f  ldarg.1
0xde20  ldloc.0
0xde21  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_PageLayoutType()
0xde26  ldarg.3
0xde27  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xde2c  ldarg.1
0xde2d  ldstr    aPromotedstate_0// "PromotedState"
0xde32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde37  ldarg.1
0xde38  ldloc.0
0xde39  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_PromotedState()
0xde3e  ldarg.3
0xde3f  call     T0x2B00003A
0xde44  ldarg.1
0xde45  ldstr    aSourceitemid// "SourceItemId"
0xde4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde4f  ldarg.1
0xde50  ldloc.0
0xde51  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_SourceItemId()
0xde56  ldarg.3
0xde57  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xde5c  ldarg.1
0xde5d  ldstr    aTitle// "Title"
0xde62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde67  ldarg.1
0xde68  ldloc.0
0xde69  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_Title()
0xde6e  ldarg.3
0xde6f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xde74  ldarg.1
0xde75  ldstr    aWebrelativefol// "WebRelativeFolderPath"
0xde7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xde7f  ldarg.1
0xde80  ldloc.0
0xde81  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_WebRelativeFolderPath()
0xde86  ldarg.3
0xde87  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xde8c  ret
```
