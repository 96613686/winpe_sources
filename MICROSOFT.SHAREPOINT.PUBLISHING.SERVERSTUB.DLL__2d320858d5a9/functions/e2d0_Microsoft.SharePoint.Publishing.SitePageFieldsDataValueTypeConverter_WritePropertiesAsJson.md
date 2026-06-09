# Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::WritePropertiesAsJson

- ea: `0xe2d0`
- end: `0xe375`
- name: `Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::WritePropertiesAsJson`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe2d0`

## string_xrefs

- `0xe315`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0xe2d0  ldarg.2
0xe2d1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData
0xe2d6  stloc.0
0xe2d7  ldloc.0
0xe2d8  brtrue.s loc_E2DB
0xe2da  ret
0xe2db  ldarg.0
0xe2dc  ldarg.1
0xe2dd  ldarg.2
0xe2de  ldarg.3
0xe2df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe2e4  ldarg.1
0xe2e5  ldstr    aBannerimageurl// "BannerImageUrl"
0xe2ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe2ef  ldarg.1
0xe2f0  ldloc.0
0xe2f1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_BannerImageUrl()
0xe2f6  ldarg.3
0xe2f7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe2fc  ldarg.1
0xe2fd  ldstr    aCanvascontent1// "CanvasContent1"
0xe302  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe307  ldarg.1
0xe308  ldloc.0
0xe309  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_CanvasContent1()
0xe30e  ldarg.3
0xe30f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe314  ldarg.1
0xe315  ldstr    aCanvasjson1// "CanvasJson1"
0xe31a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe31f  ldarg.1
0xe320  ldloc.0
0xe321  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_CanvasJson1()
0xe326  ldarg.3
0xe327  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe32c  ldarg.1
0xe32d  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xe332  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe337  ldarg.1
0xe338  ldloc.0
0xe339  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_LayoutWebpartsContent()
0xe33e  ldarg.3
0xe33f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe344  ldarg.1
0xe345  ldstr    aModified// "Modified"
0xe34a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe34f  ldarg.1
0xe350  ldloc.0
0xe351  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_Modified()
0xe356  ldarg.3
0xe357  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe35c  ldarg.1
0xe35d  ldstr    aTitle// "Title"
0xe362  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xe367  ldarg.1
0xe368  ldloc.0
0xe369  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_Title()
0xe36e  ldarg.3
0xe36f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe374  ret
```
