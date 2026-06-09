# Microsoft.SharePoint.ServerStub.SPListTemplateServerStub::WritePropertiesAsJson

- ea: `0x6af90`
- end: `0x6b25d`
- name: `Microsoft.SharePoint.ServerStub.SPListTemplateServerStub::WritePropertiesAsJson`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6af90`

## string_xrefs

- `0x6b13b`: `IsCustomTemplate`
- `0x6b147`: `IsCustomTemplate`
- `0x6b152`: `IsCustomTemplate`
- `0x6b16a`: `IsCustomTemplate`
- `0x6b1e9`: `ListTemplateTypeKind`
- `0x6b1f5`: `ListTemplateTypeKind`
- `0x6b200`: `ListTemplateTypeKind`
- `0x6b218`: `ListTemplateTypeKind`

## pseudocode

```c

```

## disassembly

```asm
0x6af90  ldarg.2
0x6af91  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate
0x6af96  stloc.0
0x6af97  ldloc.0
0x6af98  brtrue.s loc_6AF9B
0x6af9a  ret
0x6af9b  ldarg.0
0x6af9c  ldarg.1
0x6af9d  ldarg.2
0x6af9e  ldarg.3
0x6af9f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6afa4  ldarg.0
0x6afa5  ldstr    aAllowsfoldercr// "AllowsFolderCreation"
0x6afaa  ldarg.3
0x6afab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6afb0  ldarg.1
0x6afb1  ldstr    aAllowsfoldercr// "AllowsFolderCreation"
0x6afb6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6afbb  ldarg.3
0x6afbc  ldstr    aAllowsfoldercr// "AllowsFolderCreation"
0x6afc1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6afc6  ldarg.1
0x6afc7  ldloc.0
0x6afc8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_AllowsFolderCreation()
0x6afcd  ldarg.3
0x6afce  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6afd3  ldarg.3
0x6afd4  ldstr    aAllowsfoldercr// "AllowsFolderCreation"
0x6afd9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6afde  ldarg.0
0x6afdf  ldstr    aBasetype// "BaseType"
0x6afe4  ldarg.3
0x6afe5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6afea  ldarg.1
0x6afeb  ldstr    aBasetype// "BaseType"
0x6aff0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6aff5  ldarg.3
0x6aff6  ldstr    aBasetype// "BaseType"
0x6affb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b000  ldarg.1
0x6b001  ldloc.0
0x6b002  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseType [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_BaseType()
0x6b007  ldarg.3
0x6b008  call     T0x2B000022
0x6b00d  ldarg.3
0x6b00e  ldstr    aBasetype// "BaseType"
0x6b013  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b018  ldarg.0
0x6b019  ldstr    aDescription// "Description"
0x6b01e  ldarg.3
0x6b01f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b024  ldarg.1
0x6b025  ldstr    aDescription// "Description"
0x6b02a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b02f  ldarg.3
0x6b030  ldstr    aDescription// "Description"
0x6b035  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b03a  ldarg.1
0x6b03b  ldloc.0
0x6b03c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_Description()
0x6b041  ldarg.3
0x6b042  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b047  ldarg.3
0x6b048  ldstr    aDescription// "Description"
0x6b04d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b052  ldarg.0
0x6b053  ldstr    aFeatureid_0// "FeatureId"
0x6b058  ldarg.3
0x6b059  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b05e  ldarg.1
0x6b05f  ldstr    aFeatureid_0// "FeatureId"
0x6b064  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b069  ldarg.3
0x6b06a  ldstr    aFeatureid_0// "FeatureId"
0x6b06f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b074  ldarg.1
0x6b075  ldloc.0
0x6b076  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_FeatureId()
0x6b07b  ldarg.3
0x6b07c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b081  ldarg.3
0x6b082  ldstr    aFeatureid_0// "FeatureId"
0x6b087  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b08c  ldarg.0
0x6b08d  ldstr    aHidden// "Hidden"
0x6b092  ldarg.3
0x6b093  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b098  ldarg.1
0x6b099  ldstr    aHidden// "Hidden"
0x6b09e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b0a3  ldarg.3
0x6b0a4  ldstr    aHidden// "Hidden"
0x6b0a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b0ae  ldarg.1
0x6b0af  ldloc.0
0x6b0b0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_Hidden()
0x6b0b5  ldarg.3
0x6b0b6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b0bb  ldarg.3
0x6b0bc  ldstr    aHidden// "Hidden"
0x6b0c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b0c6  ldarg.0
0x6b0c7  ldstr    aImageurl// "ImageUrl"
0x6b0cc  ldarg.3
0x6b0cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b0d2  ldarg.1
0x6b0d3  ldstr    aImageurl// "ImageUrl"
0x6b0d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b0dd  ldarg.3
0x6b0de  ldstr    aImageurl// "ImageUrl"
0x6b0e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b0e8  ldarg.1
0x6b0e9  ldloc.0
0x6b0ea  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_ImageUrl()
0x6b0ef  ldarg.3
0x6b0f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b0f5  ldarg.3
0x6b0f6  ldstr    aImageurl// "ImageUrl"
0x6b0fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b100  ldarg.0
0x6b101  ldstr    aInternalname// "InternalName"
0x6b106  ldarg.3
0x6b107  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b10c  ldarg.1
0x6b10d  ldstr    aInternalname// "InternalName"
0x6b112  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b117  ldarg.3
0x6b118  ldstr    aInternalname// "InternalName"
0x6b11d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b122  ldarg.1
0x6b123  ldloc.0
0x6b124  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_InternalName()
0x6b129  ldarg.3
0x6b12a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b12f  ldarg.3
0x6b130  ldstr    aInternalname// "InternalName"
0x6b135  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b13a  ldarg.0
0x6b13b  ldstr    aIscustomtempla// "IsCustomTemplate"
0x6b140  ldarg.3
0x6b141  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b146  ldarg.1
0x6b147  ldstr    aIscustomtempla// "IsCustomTemplate"
0x6b14c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b151  ldarg.3
0x6b152  ldstr    aIscustomtempla// "IsCustomTemplate"
0x6b157  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b15c  ldarg.1
0x6b15d  ldloc.0
0x6b15e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_IsCustomTemplate()
0x6b163  ldarg.3
0x6b164  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b169  ldarg.3
0x6b16a  ldstr    aIscustomtempla// "IsCustomTemplate"
0x6b16f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b174  ldarg.0
0x6b175  ldstr    aName// "Name"
0x6b17a  ldarg.3
0x6b17b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b180  ldarg.1
0x6b181  ldstr    aName// "Name"
0x6b186  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b18b  ldarg.3
0x6b18c  ldstr    aName// "Name"
0x6b191  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b196  ldarg.1
0x6b197  ldloc.0
0x6b198  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_Name()
0x6b19d  ldarg.3
0x6b19e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b1a3  ldarg.3
0x6b1a4  ldstr    aName// "Name"
0x6b1a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b1ae  ldarg.0
0x6b1af  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x6b1b4  ldarg.3
0x6b1b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b1ba  ldarg.1
0x6b1bb  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x6b1c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b1c5  ldarg.3
0x6b1c6  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x6b1cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b1d0  ldarg.1
0x6b1d1  ldloc.0
0x6b1d2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_OnQuickLaunch()
0x6b1d7  ldarg.3
0x6b1d8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b1dd  ldarg.3
0x6b1de  ldstr    aOnquicklaunch// "OnQuickLaunch"
0x6b1e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b1e8  ldarg.0
0x6b1e9  ldstr    aListtemplatety_0// "ListTemplateTypeKind"
0x6b1ee  ldarg.3
0x6b1ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b1f4  ldarg.1
0x6b1f5  ldstr    aListtemplatety_0// "ListTemplateTypeKind"
0x6b1fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b1ff  ldarg.3
0x6b200  ldstr    aListtemplatety_0// "ListTemplateTypeKind"
0x6b205  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b20a  ldarg.1
0x6b20b  ldloc.0
0x6b20c  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_Type_Client()
0x6b211  ldarg.3
0x6b212  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b217  ldarg.3
0x6b218  ldstr    aListtemplatety_0// "ListTemplateTypeKind"
0x6b21d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b222  ldarg.0
0x6b223  ldstr    aUnique// "Unique"
0x6b228  ldarg.3
0x6b229  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b22e  ldarg.1
0x6b22f  ldstr    aUnique// "Unique"
0x6b234  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6b239  ldarg.3
0x6b23a  ldstr    aUnique// "Unique"
0x6b23f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6b244  ldarg.1
0x6b245  ldloc.0
0x6b246  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPListTemplate::get_Unique()
0x6b24b  ldarg.3
0x6b24c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6b251  ldarg.3
0x6b252  ldstr    aUnique// "Unique"
0x6b257  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6b25c  ret
```
