# Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::WritePropertiesAsJson

- ea: `0x1cf0`
- end: `0x1dc5`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::WritePropertiesAsJson`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1cf0`

## string_xrefs

- `0x1dad`: `WebTemplateExtensionId`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldarg.2
0x1cf1  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest
0x1cf6  stloc.0
0x1cf7  ldloc.0
0x1cf8  brtrue.s loc_1CFB
0x1cfa  ret
0x1cfb  ldarg.0
0x1cfc  ldarg.1
0x1cfd  ldarg.2
0x1cfe  ldarg.3
0x1cff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d04  ldarg.1
0x1d05  ldstr    aAllowfileshari// "AllowFileSharingForGuestUsers"
0x1d0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d0f  ldarg.1
0x1d10  ldloc.0
0x1d11  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_AllowFileSharingForGuestUsers()
0x1d16  ldarg.3
0x1d17  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d1c  ldarg.1
0x1d1d  ldstr    aClassification// "Classification"
0x1d22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d27  ldarg.1
0x1d28  ldloc.0
0x1d29  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Classification()
0x1d2e  ldarg.3
0x1d2f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d34  ldarg.1
0x1d35  ldstr    aDescription// "Description"
0x1d3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d3f  ldarg.1
0x1d40  ldloc.0
0x1d41  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Description()
0x1d46  ldarg.3
0x1d47  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d4c  ldarg.1
0x1d4d  ldstr    aLcid_0// "lcid"
0x1d52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d57  ldarg.1
0x1d58  ldloc.0
0x1d59  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_lcid()
0x1d5e  ldarg.3
0x1d5f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d64  ldarg.1
0x1d65  ldstr    aSitedesignid// "SiteDesignId"
0x1d6a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d6f  ldarg.1
0x1d70  ldloc.0
0x1d71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_SiteDesignId()
0x1d76  ldarg.3
0x1d77  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d7c  ldarg.1
0x1d7d  ldstr    aTitle// "Title"
0x1d82  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d87  ldarg.1
0x1d88  ldloc.0
0x1d89  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Title()
0x1d8e  ldarg.3
0x1d8f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1d94  ldarg.1
0x1d95  ldstr    aUrl// "Url"
0x1d9a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1d9f  ldarg.1
0x1da0  ldloc.0
0x1da1  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_Url()
0x1da6  ldarg.3
0x1da7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1dac  ldarg.1
0x1dad  ldstr    aWebtemplateext// "WebTemplateExtensionId"
0x1db2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x1db7  ldarg.1
0x1db8  ldloc.0
0x1db9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest::get_WebTemplateExtensionId()
0x1dbe  ldarg.3
0x1dbf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1dc4  ret
```
