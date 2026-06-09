# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::WritePropertiesAsJson

- ea: `0x64da0`
- end: `0x6511b`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementFileSettingsServerStub::WritePropertiesAsJson`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x64da0`

## string_xrefs

- `0x64e29`: `AllowWriteCopy`
- `0x64e35`: `AllowWriteCopy`
- `0x64e40`: `AllowWriteCopy`
- `0x64e58`: `AllowWriteCopy`
- `0x64e9d`: `DocumentAccessExpireDays`
- `0x64ea9`: `DocumentAccessExpireDays`
- `0x64eb4`: `DocumentAccessExpireDays`
- `0x64ecc`: `DocumentAccessExpireDays`
- `0x64ed7`: `EnableDocumentAccessExpire`
- `0x64ee3`: `EnableDocumentAccessExpire`
- `0x64eee`: `EnableDocumentAccessExpire`
- `0x64f06`: `EnableDocumentAccessExpire`
- `0x64f85`: `EnableLicenseCacheExpire`
- `0x64f91`: `EnableLicenseCacheExpire`
- `0x64f9c`: `EnableLicenseCacheExpire`
- `0x64fb4`: `EnableLicenseCacheExpire`
- `0x65033`: `LicenseCacheExpireDays`
- `0x6503f`: `LicenseCacheExpireDays`
- `0x6504a`: `LicenseCacheExpireDays`
- `0x65062`: `LicenseCacheExpireDays`
- `0x650e1`: `TemplateId`
- `0x650ed`: `TemplateId`
- `0x650f8`: `TemplateId`
- `0x65110`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x64da0  ldarg.2
0x64da1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings
0x64da6  stloc.0
0x64da7  ldloc.0
0x64da8  brtrue.s loc_64DAB
0x64daa  ret
0x64dab  ldarg.0
0x64dac  ldarg.1
0x64dad  ldarg.2
0x64dae  ldarg.3
0x64daf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64db4  ldarg.0
0x64db5  ldstr    aAllowprint// "AllowPrint"
0x64dba  ldarg.3
0x64dbb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64dc0  ldarg.1
0x64dc1  ldstr    aAllowprint// "AllowPrint"
0x64dc6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64dcb  ldarg.3
0x64dcc  ldstr    aAllowprint// "AllowPrint"
0x64dd1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64dd6  ldarg.1
0x64dd7  ldloc.0
0x64dd8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowPrint()
0x64ddd  ldarg.3
0x64dde  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64de3  ldarg.3
0x64de4  ldstr    aAllowprint// "AllowPrint"
0x64de9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64dee  ldarg.0
0x64def  ldstr    aAllowscript// "AllowScript"
0x64df4  ldarg.3
0x64df5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64dfa  ldarg.1
0x64dfb  ldstr    aAllowscript// "AllowScript"
0x64e00  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64e05  ldarg.3
0x64e06  ldstr    aAllowscript// "AllowScript"
0x64e0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64e10  ldarg.1
0x64e11  ldloc.0
0x64e12  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowScript()
0x64e17  ldarg.3
0x64e18  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e1d  ldarg.3
0x64e1e  ldstr    aAllowscript// "AllowScript"
0x64e23  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64e28  ldarg.0
0x64e29  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64e2e  ldarg.3
0x64e2f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e34  ldarg.1
0x64e35  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64e3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64e3f  ldarg.3
0x64e40  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64e45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64e4a  ldarg.1
0x64e4b  ldloc.0
0x64e4c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_AllowWriteCopy()
0x64e51  ldarg.3
0x64e52  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e57  ldarg.3
0x64e58  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x64e5d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64e62  ldarg.0
0x64e63  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64e68  ldarg.3
0x64e69  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e6e  ldarg.1
0x64e6f  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64e74  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64e79  ldarg.3
0x64e7a  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64e7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64e84  ldarg.1
0x64e85  ldloc.0
0x64e86  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DisableDocumentBrowserView()
0x64e8b  ldarg.3
0x64e8c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64e91  ldarg.3
0x64e92  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x64e97  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64e9c  ldarg.0
0x64e9d  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64ea2  ldarg.3
0x64ea3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64ea8  ldarg.1
0x64ea9  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64eae  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64eb3  ldarg.3
0x64eb4  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64eb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64ebe  ldarg.1
0x64ebf  ldloc.0
0x64ec0  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_DocumentAccessExpireDays()
0x64ec5  ldarg.3
0x64ec6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64ecb  ldarg.3
0x64ecc  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x64ed1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64ed6  ldarg.0
0x64ed7  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64edc  ldarg.3
0x64edd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64ee2  ldarg.1
0x64ee3  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64ee8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64eed  ldarg.3
0x64eee  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64ef3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64ef8  ldarg.1
0x64ef9  ldloc.0
0x64efa  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentAccessExpire()
0x64eff  ldarg.3
0x64f00  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f05  ldarg.3
0x64f06  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x64f0b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64f10  ldarg.0
0x64f11  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64f16  ldarg.3
0x64f17  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f1c  ldarg.1
0x64f1d  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64f22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64f27  ldarg.3
0x64f28  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64f2d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64f32  ldarg.1
0x64f33  ldloc.0
0x64f34  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableDocumentBrowserPublishingView()
0x64f39  ldarg.3
0x64f3a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f3f  ldarg.3
0x64f40  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x64f45  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64f4a  ldarg.0
0x64f4b  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64f50  ldarg.3
0x64f51  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f56  ldarg.1
0x64f57  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64f5c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64f61  ldarg.3
0x64f62  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64f67  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64f6c  ldarg.1
0x64f6d  ldloc.0
0x64f6e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableGroupProtection()
0x64f73  ldarg.3
0x64f74  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f79  ldarg.3
0x64f7a  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x64f7f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64f84  ldarg.0
0x64f85  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x64f8a  ldarg.3
0x64f8b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64f90  ldarg.1
0x64f91  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x64f96  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64f9b  ldarg.3
0x64f9c  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x64fa1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64fa6  ldarg.1
0x64fa7  ldloc.0
0x64fa8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_EnableLicenseCacheExpire()
0x64fad  ldarg.3
0x64fae  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64fb3  ldarg.3
0x64fb4  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x64fb9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64fbe  ldarg.0
0x64fbf  ldstr    aGroupname// "GroupName"
0x64fc4  ldarg.3
0x64fc5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64fca  ldarg.1
0x64fcb  ldstr    aGroupname// "GroupName"
0x64fd0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x64fd5  ldarg.3
0x64fd6  ldstr    aGroupname// "GroupName"
0x64fdb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x64fe0  ldarg.1
0x64fe1  ldloc.0
0x64fe2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_GroupName()
0x64fe7  ldarg.3
0x64fe8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x64fed  ldarg.3
0x64fee  ldstr    aGroupname// "GroupName"
0x64ff3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x64ff8  ldarg.0
0x64ff9  ldstr    aIrmenabled// "IrmEnabled"
0x64ffe  ldarg.3
0x64fff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65004  ldarg.1
0x65005  ldstr    aIrmenabled// "IrmEnabled"
0x6500a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6500f  ldarg.3
0x65010  ldstr    aIrmenabled// "IrmEnabled"
0x65015  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6501a  ldarg.1
0x6501b  ldloc.0
0x6501c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_IrmEnabled()
0x65021  ldarg.3
0x65022  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65027  ldarg.3
0x65028  ldstr    aIrmenabled// "IrmEnabled"
0x6502d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x65032  ldarg.0
0x65033  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65038  ldarg.3
0x65039  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6503e  ldarg.1
0x6503f  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65044  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x65049  ldarg.3
0x6504a  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x6504f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x65054  ldarg.1
0x65055  ldloc.0
0x65056  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_LicenseCacheExpireDays()
0x6505b  ldarg.3
0x6505c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65061  ldarg.3
0x65062  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x65067  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6506c  ldarg.0
0x6506d  ldstr    aPolicydescript// "PolicyDescription"
0x65072  ldarg.3
0x65073  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x65078  ldarg.1
0x65079  ldstr    aPolicydescript// "PolicyDescription"
0x6507e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x65083  ldarg.3
0x65084  ldstr    aPolicydescript// "PolicyDescription"
0x65089  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6508e  ldarg.1
0x6508f  ldloc.0
0x65090  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_PolicyDescription()
0x65095  ldarg.3
0x65096  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6509b  ldarg.3
0x6509c  ldstr    aPolicydescript// "PolicyDescription"
0x650a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x650a6  ldarg.0
0x650a7  ldstr    aPolicytitle// "PolicyTitle"
0x650ac  ldarg.3
0x650ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x650b2  ldarg.1
0x650b3  ldstr    aPolicytitle// "PolicyTitle"
0x650b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x650bd  ldarg.3
0x650be  ldstr    aPolicytitle// "PolicyTitle"
0x650c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x650c8  ldarg.1
0x650c9  ldloc.0
0x650ca  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_PolicyTitle()
0x650cf  ldarg.3
0x650d0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x650d5  ldarg.3
0x650d6  ldstr    aPolicytitle// "PolicyTitle"
0x650db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x650e0  ldarg.0
0x650e1  ldstr    aTemplateid// "TemplateId"
0x650e6  ldarg.3
0x650e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x650ec  ldarg.1
0x650ed  ldstr    aTemplateid// "TemplateId"
0x650f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x650f7  ldarg.3
0x650f8  ldstr    aTemplateid// "TemplateId"
0x650fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x65102  ldarg.1
0x65103  ldloc.0
0x65104  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementFileSettings::get_TemplateId()
0x65109  ldarg.3
0x6510a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6510f  ldarg.3
0x65110  ldstr    aTemplateid// "TemplateId"
0x65115  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6511a  ret
```
