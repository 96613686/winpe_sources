# Microsoft.SharePoint.ServerStub.SPWebServerStub::WritePropertiesAsJson

- ea: `0x98bf0`
- end: `0x993b9`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::WritePropertiesAsJson`
- size: `1993`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x98bf0`

## string_xrefs

- `0x98ced`: `Created`
- `0x98cf9`: `Created`
- `0x98d04`: `Created`
- `0x98d1c`: `Created`
- `0x98d27`: `CurrentChangeToken`
- `0x98d33`: `CurrentChangeToken`
- `0x98d3e`: `CurrentChangeToken`
- `0x98d56`: `CurrentChangeToken`
- `0x9937f`: `WelcomePage`
- `0x9938b`: `WelcomePage`
- `0x99396`: `WelcomePage`
- `0x993ae`: `WelcomePage`
- `0x990c7`: `ResourcePath`
- `0x990d3`: `ResourcePath`
- `0x990de`: `ResourcePath`
- `0x990f6`: `ResourcePath`
- `0x992d1`: `UIVersionConfigurationEnabled`
- `0x992dd`: `UIVersionConfigurationEnabled`
- `0x992e8`: `UIVersionConfigurationEnabled`
- `0x99300`: `UIVersionConfigurationEnabled`
- `0x99345`: `WebTemplate`
- `0x99351`: `WebTemplate`
- `0x9935c`: `WebTemplate`
- `0x99374`: `WebTemplate`
- `0x98cb3`: `Configuration`
- `0x98cbf`: `Configuration`
- `0x98cca`: `Configuration`
- `0x98ce2`: `Configuration`
- `0x9908d`: `OverwriteTranslationsOnChange`
- `0x99099`: `OverwriteTranslationsOnChange`
- `0x990a4`: `OverwriteTranslationsOnChange`
- `0x990bc`: `OverwriteTranslationsOnChange`

## pseudocode

```c

```

## disassembly

```asm
0x98bf0  ldarg.2
0x98bf1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb
0x98bf6  stloc.0
0x98bf7  ldloc.0
0x98bf8  brtrue.s loc_98BFB
0x98bfa  ret
0x98bfb  ldarg.0
0x98bfc  ldarg.1
0x98bfd  ldarg.2
0x98bfe  ldarg.3
0x98bff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c04  ldarg.0
0x98c05  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x98c0a  ldarg.3
0x98c0b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c10  ldarg.1
0x98c11  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x98c16  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98c1b  ldarg.3
0x98c1c  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x98c21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98c26  ldarg.1
0x98c27  ldloc.0
0x98c28  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_AllowRssFeeds()
0x98c2d  ldarg.3
0x98c2e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c33  ldarg.3
0x98c34  ldstr    aAllowrssfeeds// "AllowRssFeeds"
0x98c39  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98c3e  ldarg.0
0x98c3f  ldstr    aAlternatecssur// "AlternateCssUrl"
0x98c44  ldarg.3
0x98c45  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c4a  ldarg.1
0x98c4b  ldstr    aAlternatecssur// "AlternateCssUrl"
0x98c50  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98c55  ldarg.3
0x98c56  ldstr    aAlternatecssur// "AlternateCssUrl"
0x98c5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98c60  ldarg.1
0x98c61  ldloc.0
0x98c62  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_AlternateCssUrl()
0x98c67  ldarg.3
0x98c68  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c6d  ldarg.3
0x98c6e  ldstr    aAlternatecssur// "AlternateCssUrl"
0x98c73  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98c78  ldarg.0
0x98c79  ldstr    aAppinstanceid_1// "AppInstanceId"
0x98c7e  ldarg.3
0x98c7f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98c84  ldarg.1
0x98c85  ldstr    aAppinstanceid_1// "AppInstanceId"
0x98c8a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98c8f  ldarg.3
0x98c90  ldstr    aAppinstanceid_1// "AppInstanceId"
0x98c95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98c9a  ldarg.1
0x98c9b  ldloc.0
0x98c9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_AppInstanceId()
0x98ca1  ldarg.3
0x98ca2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98ca7  ldarg.3
0x98ca8  ldstr    aAppinstanceid_1// "AppInstanceId"
0x98cad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98cb2  ldarg.0
0x98cb3  ldstr    aConfiguration// "Configuration"
0x98cb8  ldarg.3
0x98cb9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98cbe  ldarg.1
0x98cbf  ldstr    aConfiguration// "Configuration"
0x98cc4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98cc9  ldarg.3
0x98cca  ldstr    aConfiguration// "Configuration"
0x98ccf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98cd4  ldarg.1
0x98cd5  ldloc.0
0x98cd6  callvirt instance int16 [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Configuration()
0x98cdb  ldarg.3
0x98cdc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt16(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int16, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98ce1  ldarg.3
0x98ce2  ldstr    aConfiguration// "Configuration"
0x98ce7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98cec  ldarg.0
0x98ced  ldstr    aCreated// "Created"
0x98cf2  ldarg.3
0x98cf3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98cf8  ldarg.1
0x98cf9  ldstr    aCreated// "Created"
0x98cfe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98d03  ldarg.3
0x98d04  ldstr    aCreated// "Created"
0x98d09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98d0e  ldarg.1
0x98d0f  ldloc.0
0x98d10  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Created()
0x98d15  ldarg.3
0x98d16  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98d1b  ldarg.3
0x98d1c  ldstr    aCreated// "Created"
0x98d21  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98d26  ldarg.0
0x98d27  ldstr    aCurrentchanget// "CurrentChangeToken"
0x98d2c  ldarg.3
0x98d2d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98d32  ldarg.1
0x98d33  ldstr    aCurrentchanget// "CurrentChangeToken"
0x98d38  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98d3d  ldarg.3
0x98d3e  ldstr    aCurrentchanget// "CurrentChangeToken"
0x98d43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98d48  ldarg.1
0x98d49  ldloc.0
0x98d4a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_CurrentChangeToken()
0x98d4f  ldarg.3
0x98d50  call     T0x2B000024
0x98d55  ldarg.3
0x98d56  ldstr    aCurrentchanget// "CurrentChangeToken"
0x98d5b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98d60  ldarg.0
0x98d61  ldstr    aCustommasterur// "CustomMasterUrl"
0x98d66  ldarg.3
0x98d67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98d6c  ldarg.1
0x98d6d  ldstr    aCustommasterur// "CustomMasterUrl"
0x98d72  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98d77  ldarg.3
0x98d78  ldstr    aCustommasterur// "CustomMasterUrl"
0x98d7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98d82  ldarg.1
0x98d83  ldloc.0
0x98d84  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_CustomMasterUrl()
0x98d89  ldarg.3
0x98d8a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98d8f  ldarg.3
0x98d90  ldstr    aCustommasterur// "CustomMasterUrl"
0x98d95  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98d9a  ldarg.0
0x98d9b  ldstr    aDescription// "Description"
0x98da0  ldarg.3
0x98da1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98da6  ldarg.1
0x98da7  ldstr    aDescription// "Description"
0x98dac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98db1  ldarg.3
0x98db2  ldstr    aDescription// "Description"
0x98db7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98dbc  ldarg.1
0x98dbd  ldloc.0
0x98dbe  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Description()
0x98dc3  ldarg.3
0x98dc4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98dc9  ldarg.3
0x98dca  ldstr    aDescription// "Description"
0x98dcf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98dd4  ldarg.0
0x98dd5  ldstr    aDesignpackagei// "DesignPackageId"
0x98dda  ldarg.3
0x98ddb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98de0  ldarg.1
0x98de1  ldstr    aDesignpackagei// "DesignPackageId"
0x98de6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98deb  ldarg.3
0x98dec  ldstr    aDesignpackagei// "DesignPackageId"
0x98df1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98df6  ldarg.1
0x98df7  ldloc.0
0x98df8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_DesignPackageId()
0x98dfd  ldarg.3
0x98dfe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e03  ldarg.3
0x98e04  ldstr    aDesignpackagei// "DesignPackageId"
0x98e09  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98e0e  ldarg.0
0x98e0f  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x98e14  ldarg.3
0x98e15  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e1a  ldarg.1
0x98e1b  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x98e20  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98e25  ldarg.3
0x98e26  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x98e2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98e30  ldarg.1
0x98e31  ldloc.0
0x98e32  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_DocumentLibraryCalloutOfficeWebAppPreviewersDisabled()
0x98e37  ldarg.3
0x98e38  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e3d  ldarg.3
0x98e3e  ldstr    aDocumentlibrar_1// "DocumentLibraryCalloutOfficeWebAppPrevi"...
0x98e43  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98e48  ldarg.0
0x98e49  ldstr    aEnableminimald// "EnableMinimalDownload"
0x98e4e  ldarg.3
0x98e4f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e54  ldarg.1
0x98e55  ldstr    aEnableminimald// "EnableMinimalDownload"
0x98e5a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98e5f  ldarg.3
0x98e60  ldstr    aEnableminimald// "EnableMinimalDownload"
0x98e65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98e6a  ldarg.1
0x98e6b  ldloc.0
0x98e6c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_EnableMinimalDownload()
0x98e71  ldarg.3
0x98e72  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e77  ldarg.3
0x98e78  ldstr    aEnableminimald// "EnableMinimalDownload"
0x98e7d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98e82  ldarg.0
0x98e83  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x98e88  ldarg.3
0x98e89  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98e8e  ldarg.1
0x98e8f  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x98e94  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98e99  ldarg.3
0x98e9a  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x98e9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98ea4  ldarg.1
0x98ea5  ldloc.0
0x98ea6  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPVariantThemeType [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_HeaderEmphasis()
0x98eab  ldarg.3
0x98eac  call     T0x2B00024B
0x98eb1  ldarg.3
0x98eb2  ldstr    aHeaderemphasis// "HeaderEmphasis"
0x98eb7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98ebc  ldarg.0
0x98ebd  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x98ec2  ldarg.3
0x98ec3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98ec8  ldarg.1
0x98ec9  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x98ece  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98ed3  ldarg.3
0x98ed4  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x98ed9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98ede  ldarg.1
0x98edf  ldloc.0
0x98ee0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_HorizontalQuickLaunch()
0x98ee5  ldarg.3
0x98ee6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98eeb  ldarg.3
0x98eec  ldstr    aHorizontalquic// "HorizontalQuickLaunch"
0x98ef1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98ef6  ldarg.0
0x98ef7  ldstr    aId_0// "Id"
0x98efc  ldarg.3
0x98efd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f02  ldarg.1
0x98f03  ldstr    aId_0// "Id"
0x98f08  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98f0d  ldarg.3
0x98f0e  ldstr    aId_0// "Id"
0x98f13  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98f18  ldarg.1
0x98f19  ldloc.0
0x98f1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x98f1f  ldarg.3
0x98f20  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f25  ldarg.3
0x98f26  ldstr    aId_0// "Id"
0x98f2b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98f30  ldarg.0
0x98f31  ldstr    aIsmultilingual// "IsMultilingual"
0x98f36  ldarg.3
0x98f37  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f3c  ldarg.1
0x98f3d  ldstr    aIsmultilingual// "IsMultilingual"
0x98f42  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98f47  ldarg.3
0x98f48  ldstr    aIsmultilingual// "IsMultilingual"
0x98f4d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98f52  ldarg.1
0x98f53  ldloc.0
0x98f54  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_IsMultilingual()
0x98f59  ldarg.3
0x98f5a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f5f  ldarg.3
0x98f60  ldstr    aIsmultilingual// "IsMultilingual"
0x98f65  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98f6a  ldarg.0
0x98f6b  ldstr    aLanguage// "Language"
0x98f70  ldarg.3
0x98f71  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f76  ldarg.1
0x98f77  ldstr    aLanguage// "Language"
0x98f7c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x98f81  ldarg.3
0x98f82  ldstr    aLanguage// "Language"
0x98f87  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x98f8c  ldarg.1
0x98f8d  ldloc.0
0x98f8e  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Language()
0x98f93  ldarg.3
0x98f94  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteUInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, unsigned int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x98f99  ldarg.3
0x98f9a  ldstr    aLanguage// "Language"
0x98f9f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x98fa4  ldarg.0
  ... truncated ...
```
