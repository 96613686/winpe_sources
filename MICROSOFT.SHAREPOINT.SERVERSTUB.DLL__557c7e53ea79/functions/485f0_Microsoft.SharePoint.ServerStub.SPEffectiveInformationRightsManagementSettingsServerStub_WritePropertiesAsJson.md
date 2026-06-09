# Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::WritePropertiesAsJson

- ea: `0x485f0`
- end: `0x489df`
- name: `Microsoft.SharePoint.ServerStub.SPEffectiveInformationRightsManagementSettingsServerStub::WritePropertiesAsJson`
- size: `1007`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x485f0`

## string_xrefs

- `0x48679`: `AllowWriteCopy`
- `0x48685`: `AllowWriteCopy`
- `0x48690`: `AllowWriteCopy`
- `0x486a8`: `AllowWriteCopy`
- `0x486ed`: `DocumentAccessExpireDays`
- `0x486f9`: `DocumentAccessExpireDays`
- `0x48704`: `DocumentAccessExpireDays`
- `0x4871c`: `DocumentAccessExpireDays`
- `0x48761`: `EnableDocumentAccessExpire`
- `0x4876d`: `EnableDocumentAccessExpire`
- `0x48778`: `EnableDocumentAccessExpire`
- `0x48790`: `EnableDocumentAccessExpire`
- `0x4880f`: `EnableLicenseCacheExpire`
- `0x4881b`: `EnableLicenseCacheExpire`
- `0x48826`: `EnableLicenseCacheExpire`
- `0x4883e`: `EnableLicenseCacheExpire`
- `0x488bd`: `LicenseCacheExpireDays`
- `0x488c9`: `LicenseCacheExpireDays`
- `0x488d4`: `LicenseCacheExpireDays`
- `0x488ec`: `LicenseCacheExpireDays`
- `0x489a5`: `TemplateId`
- `0x489b1`: `TemplateId`
- `0x489bc`: `TemplateId`
- `0x489d4`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x485f0  ldarg.2
0x485f1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings
0x485f6  stloc.0
0x485f7  ldloc.0
0x485f8  brtrue.s loc_485FB
0x485fa  ret
0x485fb  ldarg.0
0x485fc  ldarg.1
0x485fd  ldarg.2
0x485fe  ldarg.3
0x485ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48604  ldarg.0
0x48605  ldstr    aAllowprint// "AllowPrint"
0x4860a  ldarg.3
0x4860b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48610  ldarg.1
0x48611  ldstr    aAllowprint// "AllowPrint"
0x48616  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4861b  ldarg.3
0x4861c  ldstr    aAllowprint// "AllowPrint"
0x48621  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48626  ldarg.1
0x48627  ldloc.0
0x48628  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowPrint()
0x4862d  ldarg.3
0x4862e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48633  ldarg.3
0x48634  ldstr    aAllowprint// "AllowPrint"
0x48639  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4863e  ldarg.0
0x4863f  ldstr    aAllowscript// "AllowScript"
0x48644  ldarg.3
0x48645  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4864a  ldarg.1
0x4864b  ldstr    aAllowscript// "AllowScript"
0x48650  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48655  ldarg.3
0x48656  ldstr    aAllowscript// "AllowScript"
0x4865b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48660  ldarg.1
0x48661  ldloc.0
0x48662  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowScript()
0x48667  ldarg.3
0x48668  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4866d  ldarg.3
0x4866e  ldstr    aAllowscript// "AllowScript"
0x48673  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48678  ldarg.0
0x48679  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x4867e  ldarg.3
0x4867f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48684  ldarg.1
0x48685  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x4868a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4868f  ldarg.3
0x48690  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x48695  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4869a  ldarg.1
0x4869b  ldloc.0
0x4869c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_AllowWriteCopy()
0x486a1  ldarg.3
0x486a2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x486a7  ldarg.3
0x486a8  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x486ad  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x486b2  ldarg.0
0x486b3  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x486b8  ldarg.3
0x486b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x486be  ldarg.1
0x486bf  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x486c4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x486c9  ldarg.3
0x486ca  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x486cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x486d4  ldarg.1
0x486d5  ldloc.0
0x486d6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x486db  ldarg.3
0x486dc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x486e1  ldarg.3
0x486e2  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x486e7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x486ec  ldarg.0
0x486ed  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x486f2  ldarg.3
0x486f3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x486f8  ldarg.1
0x486f9  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x486fe  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48703  ldarg.3
0x48704  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x48709  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4870e  ldarg.1
0x4870f  ldloc.0
0x48710  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x48715  ldarg.3
0x48716  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4871b  ldarg.3
0x4871c  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x48721  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48726  ldarg.0
0x48727  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x4872c  ldarg.3
0x4872d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48732  ldarg.1
0x48733  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x48738  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4873d  ldarg.3
0x4873e  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x48743  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48748  ldarg.1
0x48749  ldloc.0
0x4874a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x4874f  ldarg.3
0x48750  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48755  ldarg.3
0x48756  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x4875b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48760  ldarg.0
0x48761  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x48766  ldarg.3
0x48767  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4876c  ldarg.1
0x4876d  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x48772  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48777  ldarg.3
0x48778  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x4877d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48782  ldarg.1
0x48783  ldloc.0
0x48784  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x48789  ldarg.3
0x4878a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4878f  ldarg.3
0x48790  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x48795  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4879a  ldarg.0
0x4879b  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x487a0  ldarg.3
0x487a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x487a6  ldarg.1
0x487a7  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x487ac  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x487b1  ldarg.3
0x487b2  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x487b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x487bc  ldarg.1
0x487bd  ldloc.0
0x487be  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableDocumentBrowserPublishingView()
0x487c3  ldarg.3
0x487c4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x487c9  ldarg.3
0x487ca  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x487cf  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x487d4  ldarg.0
0x487d5  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x487da  ldarg.3
0x487db  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x487e0  ldarg.1
0x487e1  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x487e6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x487eb  ldarg.3
0x487ec  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x487f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x487f6  ldarg.1
0x487f7  ldloc.0
0x487f8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableGroupProtection()
0x487fd  ldarg.3
0x487fe  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48803  ldarg.3
0x48804  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x48809  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4880e  ldarg.0
0x4880f  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x48814  ldarg.3
0x48815  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4881a  ldarg.1
0x4881b  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x48820  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48825  ldarg.3
0x48826  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x4882b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48830  ldarg.1
0x48831  ldloc.0
0x48832  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_EnableLicenseCacheExpire()
0x48837  ldarg.3
0x48838  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4883d  ldarg.3
0x4883e  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x48843  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48848  ldarg.0
0x48849  ldstr    aGroupname// "GroupName"
0x4884e  ldarg.3
0x4884f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48854  ldarg.1
0x48855  ldstr    aGroupname// "GroupName"
0x4885a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4885f  ldarg.3
0x48860  ldstr    aGroupname// "GroupName"
0x48865  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4886a  ldarg.1
0x4886b  ldloc.0
0x4886c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_GroupName()
0x48871  ldarg.3
0x48872  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48877  ldarg.3
0x48878  ldstr    aGroupname// "GroupName"
0x4887d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48882  ldarg.0
0x48883  ldstr    aIrmenabled// "IrmEnabled"
0x48888  ldarg.3
0x48889  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4888e  ldarg.1
0x4888f  ldstr    aIrmenabled// "IrmEnabled"
0x48894  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48899  ldarg.3
0x4889a  ldstr    aIrmenabled// "IrmEnabled"
0x4889f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x488a4  ldarg.1
0x488a5  ldloc.0
0x488a6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_IrmEnabled()
0x488ab  ldarg.3
0x488ac  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x488b1  ldarg.3
0x488b2  ldstr    aIrmenabled// "IrmEnabled"
0x488b7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x488bc  ldarg.0
0x488bd  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x488c2  ldarg.3
0x488c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x488c8  ldarg.1
0x488c9  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x488ce  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x488d3  ldarg.3
0x488d4  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x488d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x488de  ldarg.1
0x488df  ldloc.0
0x488e0  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_LicenseCacheExpireDays()
0x488e5  ldarg.3
0x488e6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x488eb  ldarg.3
0x488ec  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x488f1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x488f6  ldarg.0
0x488f7  ldstr    aPolicydescript// "PolicyDescription"
0x488fc  ldarg.3
0x488fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48902  ldarg.1
0x48903  ldstr    aPolicydescript// "PolicyDescription"
0x48908  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x4890d  ldarg.3
0x4890e  ldstr    aPolicydescript// "PolicyDescription"
0x48913  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48918  ldarg.1
0x48919  ldloc.0
0x4891a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_PolicyDescription()
0x4891f  ldarg.3
0x48920  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48925  ldarg.3
0x48926  ldstr    aPolicydescript// "PolicyDescription"
0x4892b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x48930  ldarg.0
0x48931  ldstr    aPolicytitle// "PolicyTitle"
0x48936  ldarg.3
0x48937  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4893c  ldarg.1
0x4893d  ldstr    aPolicytitle// "PolicyTitle"
0x48942  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48947  ldarg.3
0x48948  ldstr    aPolicytitle// "PolicyTitle"
0x4894d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x48952  ldarg.1
0x48953  ldloc.0
0x48954  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_PolicyTitle()
0x48959  ldarg.3
0x4895a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4895f  ldarg.3
0x48960  ldstr    aPolicytitle// "PolicyTitle"
0x48965  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x4896a  ldarg.0
0x4896b  ldstr    aSettingsource// "SettingSource"
0x48970  ldarg.3
0x48971  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x48976  ldarg.1
0x48977  ldstr    aSettingsource// "SettingSource"
0x4897c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x48981  ldarg.3
0x48982  ldstr    aSettingsource// "SettingSource"
0x48987  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x4898c  ldarg.1
0x4898d  ldloc.0
0x4898e  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettingsSource [Microsoft.SharePoint]Microsoft.SharePoint.SPEffectiveInformationRightsManagementSettings::get_SettingSource()
0x48993  ldarg.3
0x48994  call     T0x2B000171
0x48999  ldarg.3
0x4899a  ldstr    aSettingsource// "SettingSource"
0x4899f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x489a4  ldarg.0
  ... truncated ...
```
