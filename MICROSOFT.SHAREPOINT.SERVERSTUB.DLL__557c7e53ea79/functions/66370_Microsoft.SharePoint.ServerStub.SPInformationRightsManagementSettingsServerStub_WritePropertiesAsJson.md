# Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::WritePropertiesAsJson

- ea: `0x66370`
- end: `0x666eb`
- name: `Microsoft.SharePoint.ServerStub.SPInformationRightsManagementSettingsServerStub::WritePropertiesAsJson`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x66370`

## string_xrefs

- `0x663f9`: `AllowWriteCopy`
- `0x66405`: `AllowWriteCopy`
- `0x66410`: `AllowWriteCopy`
- `0x66428`: `AllowWriteCopy`
- `0x6646d`: `DocumentAccessExpireDays`
- `0x66479`: `DocumentAccessExpireDays`
- `0x66484`: `DocumentAccessExpireDays`
- `0x6649c`: `DocumentAccessExpireDays`
- `0x664e1`: `EnableDocumentAccessExpire`
- `0x664ed`: `EnableDocumentAccessExpire`
- `0x664f8`: `EnableDocumentAccessExpire`
- `0x66510`: `EnableDocumentAccessExpire`
- `0x6658f`: `EnableLicenseCacheExpire`
- `0x6659b`: `EnableLicenseCacheExpire`
- `0x665a6`: `EnableLicenseCacheExpire`
- `0x665be`: `EnableLicenseCacheExpire`
- `0x66603`: `LicenseCacheExpireDays`
- `0x6660f`: `LicenseCacheExpireDays`
- `0x6661a`: `LicenseCacheExpireDays`
- `0x66632`: `LicenseCacheExpireDays`
- `0x666b1`: `TemplateId`
- `0x666bd`: `TemplateId`
- `0x666c8`: `TemplateId`
- `0x666e0`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x66370  ldarg.2
0x66371  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings
0x66376  stloc.0
0x66377  ldloc.0
0x66378  brtrue.s loc_6637B
0x6637a  ret
0x6637b  ldarg.0
0x6637c  ldarg.1
0x6637d  ldarg.2
0x6637e  ldarg.3
0x6637f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66384  ldarg.0
0x66385  ldstr    aAllowprint// "AllowPrint"
0x6638a  ldarg.3
0x6638b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66390  ldarg.1
0x66391  ldstr    aAllowprint// "AllowPrint"
0x66396  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6639b  ldarg.3
0x6639c  ldstr    aAllowprint// "AllowPrint"
0x663a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x663a6  ldarg.1
0x663a7  ldloc.0
0x663a8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowPrint()
0x663ad  ldarg.3
0x663ae  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x663b3  ldarg.3
0x663b4  ldstr    aAllowprint// "AllowPrint"
0x663b9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x663be  ldarg.0
0x663bf  ldstr    aAllowscript// "AllowScript"
0x663c4  ldarg.3
0x663c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x663ca  ldarg.1
0x663cb  ldstr    aAllowscript// "AllowScript"
0x663d0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x663d5  ldarg.3
0x663d6  ldstr    aAllowscript// "AllowScript"
0x663db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x663e0  ldarg.1
0x663e1  ldloc.0
0x663e2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowScript()
0x663e7  ldarg.3
0x663e8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x663ed  ldarg.3
0x663ee  ldstr    aAllowscript// "AllowScript"
0x663f3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x663f8  ldarg.0
0x663f9  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x663fe  ldarg.3
0x663ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66404  ldarg.1
0x66405  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x6640a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6640f  ldarg.3
0x66410  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x66415  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6641a  ldarg.1
0x6641b  ldloc.0
0x6641c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_AllowWriteCopy()
0x66421  ldarg.3
0x66422  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66427  ldarg.3
0x66428  ldstr    aAllowwritecopy// "AllowWriteCopy"
0x6642d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x66432  ldarg.0
0x66433  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x66438  ldarg.3
0x66439  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6643e  ldarg.1
0x6643f  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x66444  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x66449  ldarg.3
0x6644a  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x6644f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x66454  ldarg.1
0x66455  ldloc.0
0x66456  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DisableDocumentBrowserView()
0x6645b  ldarg.3
0x6645c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66461  ldarg.3
0x66462  ldstr    aDisabledocumen// "DisableDocumentBrowserView"
0x66467  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6646c  ldarg.0
0x6646d  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x66472  ldarg.3
0x66473  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66478  ldarg.1
0x66479  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x6647e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x66483  ldarg.3
0x66484  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x66489  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6648e  ldarg.1
0x6648f  ldloc.0
0x66490  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentAccessExpireDays()
0x66495  ldarg.3
0x66496  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6649b  ldarg.3
0x6649c  ldstr    aDocumentaccess// "DocumentAccessExpireDays"
0x664a1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x664a6  ldarg.0
0x664a7  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x664ac  ldarg.3
0x664ad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x664b2  ldarg.1
0x664b3  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x664b8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x664bd  ldarg.3
0x664be  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x664c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x664c8  ldarg.1
0x664c9  ldloc.0
0x664ca  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_DocumentLibraryProtectionExpireDate()
0x664cf  ldarg.3
0x664d0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x664d5  ldarg.3
0x664d6  ldstr    aDocumentlibrar// "DocumentLibraryProtectionExpireDate"
0x664db  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x664e0  ldarg.0
0x664e1  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x664e6  ldarg.3
0x664e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x664ec  ldarg.1
0x664ed  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x664f2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x664f7  ldarg.3
0x664f8  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x664fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x66502  ldarg.1
0x66503  ldloc.0
0x66504  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentAccessExpire()
0x66509  ldarg.3
0x6650a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6650f  ldarg.3
0x66510  ldstr    aEnabledocument// "EnableDocumentAccessExpire"
0x66515  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6651a  ldarg.0
0x6651b  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x66520  ldarg.3
0x66521  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66526  ldarg.1
0x66527  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x6652c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x66531  ldarg.3
0x66532  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x66537  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6653c  ldarg.1
0x6653d  ldloc.0
0x6653e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableDocumentBrowserPublishingView()
0x66543  ldarg.3
0x66544  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66549  ldarg.3
0x6654a  ldstr    aEnabledocument_0// "EnableDocumentBrowserPublishingView"
0x6654f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x66554  ldarg.0
0x66555  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x6655a  ldarg.3
0x6655b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66560  ldarg.1
0x66561  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x66566  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6656b  ldarg.3
0x6656c  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x66571  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x66576  ldarg.1
0x66577  ldloc.0
0x66578  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableGroupProtection()
0x6657d  ldarg.3
0x6657e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66583  ldarg.3
0x66584  ldstr    aEnablegrouppro// "EnableGroupProtection"
0x66589  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6658e  ldarg.0
0x6658f  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x66594  ldarg.3
0x66595  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6659a  ldarg.1
0x6659b  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x665a0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x665a5  ldarg.3
0x665a6  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x665ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x665b0  ldarg.1
0x665b1  ldloc.0
0x665b2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_EnableLicenseCacheExpire()
0x665b7  ldarg.3
0x665b8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x665bd  ldarg.3
0x665be  ldstr    aEnablelicensec// "EnableLicenseCacheExpire"
0x665c3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x665c8  ldarg.0
0x665c9  ldstr    aGroupname// "GroupName"
0x665ce  ldarg.3
0x665cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x665d4  ldarg.1
0x665d5  ldstr    aGroupname// "GroupName"
0x665da  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x665df  ldarg.3
0x665e0  ldstr    aGroupname// "GroupName"
0x665e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x665ea  ldarg.1
0x665eb  ldloc.0
0x665ec  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_GroupName()
0x665f1  ldarg.3
0x665f2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x665f7  ldarg.3
0x665f8  ldstr    aGroupname// "GroupName"
0x665fd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x66602  ldarg.0
0x66603  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x66608  ldarg.3
0x66609  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6660e  ldarg.1
0x6660f  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x66614  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x66619  ldarg.3
0x6661a  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x6661f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x66624  ldarg.1
0x66625  ldloc.0
0x66626  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_LicenseCacheExpireDays()
0x6662b  ldarg.3
0x6662c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66631  ldarg.3
0x66632  ldstr    aLicensecacheex// "LicenseCacheExpireDays"
0x66637  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6663c  ldarg.0
0x6663d  ldstr    aPolicydescript// "PolicyDescription"
0x66642  ldarg.3
0x66643  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66648  ldarg.1
0x66649  ldstr    aPolicydescript// "PolicyDescription"
0x6664e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x66653  ldarg.3
0x66654  ldstr    aPolicydescript// "PolicyDescription"
0x66659  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6665e  ldarg.1
0x6665f  ldloc.0
0x66660  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_PolicyDescription()
0x66665  ldarg.3
0x66666  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6666b  ldarg.3
0x6666c  ldstr    aPolicydescript// "PolicyDescription"
0x66671  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x66676  ldarg.0
0x66677  ldstr    aPolicytitle// "PolicyTitle"
0x6667c  ldarg.3
0x6667d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x66682  ldarg.1
0x66683  ldstr    aPolicytitle// "PolicyTitle"
0x66688  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6668d  ldarg.3
0x6668e  ldstr    aPolicytitle// "PolicyTitle"
0x66693  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x66698  ldarg.1
0x66699  ldloc.0
0x6669a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_PolicyTitle()
0x6669f  ldarg.3
0x666a0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x666a5  ldarg.3
0x666a6  ldstr    aPolicytitle// "PolicyTitle"
0x666ab  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x666b0  ldarg.0
0x666b1  ldstr    aTemplateid// "TemplateId"
0x666b6  ldarg.3
0x666b7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x666bc  ldarg.1
0x666bd  ldstr    aTemplateid// "TemplateId"
0x666c2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x666c7  ldarg.3
0x666c8  ldstr    aTemplateid// "TemplateId"
0x666cd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x666d2  ldarg.1
0x666d3  ldloc.0
0x666d4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPInformationRightsManagementSettings::get_TemplateId()
0x666d9  ldarg.3
0x666da  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x666df  ldarg.3
0x666e0  ldstr    aTemplateid// "TemplateId"
0x666e5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x666ea  ret
```
