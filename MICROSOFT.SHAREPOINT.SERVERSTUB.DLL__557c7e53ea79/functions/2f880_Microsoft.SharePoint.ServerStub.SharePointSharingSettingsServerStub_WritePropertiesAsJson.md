# Microsoft.SharePoint.ServerStub.SharePointSharingSettingsServerStub::WritePropertiesAsJson

- ea: `0x2f880`
- end: `0x2fc35`
- name: `Microsoft.SharePoint.ServerStub.SharePointSharingSettingsServerStub::WritePropertiesAsJson`
- size: `949`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x2f880`

## string_xrefs

- `0x2fa2b`: `RequiredScriptFileLinks`
- `0x2fa37`: `RequiredScriptFileLinks`
- `0x2fa42`: `RequiredScriptFileLinks`
- `0x2fa5a`: `RequiredScriptFileLinks`
- `0x2fb13`: `SharingCssLink`
- `0x2fb1f`: `SharingCssLink`
- `0x2fb2a`: `SharingCssLink`
- `0x2fb42`: `SharingCssLink`

## pseudocode

```c

```

## disassembly

```asm
0x2f880  ldarg.2
0x2f881  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings
0x2f886  stloc.0
0x2f887  ldloc.0
0x2f888  brtrue.s loc_2F88B
0x2f88a  ret
0x2f88b  ldarg.0
0x2f88c  ldarg.1
0x2f88d  ldarg.2
0x2f88e  ldarg.3
0x2f88f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f894  ldarg.0
0x2f895  ldstr    aAddtogroupmode// "AddToGroupModeName"
0x2f89a  ldarg.3
0x2f89b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f8a0  ldarg.1
0x2f8a1  ldstr    aAddtogroupmode// "AddToGroupModeName"
0x2f8a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f8ab  ldarg.3
0x2f8ac  ldstr    aAddtogroupmode// "AddToGroupModeName"
0x2f8b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f8b6  ldarg.1
0x2f8b7  ldloc.0
0x2f8b8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_AddToGroupModeName()
0x2f8bd  ldarg.3
0x2f8be  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f8c3  ldarg.3
0x2f8c4  ldstr    aAddtogroupmode// "AddToGroupModeName"
0x2f8c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f8ce  ldarg.0
0x2f8cf  ldstr    aGroupnamelines// "GroupNameLines"
0x2f8d4  ldarg.3
0x2f8d5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f8da  ldarg.1
0x2f8db  ldstr    aGroupnamelines// "GroupNameLines"
0x2f8e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f8e5  ldarg.3
0x2f8e6  ldstr    aGroupnamelines// "GroupNameLines"
0x2f8eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f8f0  ldarg.1
0x2f8f1  ldloc.0
0x2f8f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_GroupNameLines()
0x2f8f7  ldarg.3
0x2f8f8  call     T0x2B000114
0x2f8fd  ldarg.3
0x2f8fe  ldstr    aGroupnamelines// "GroupNameLines"
0x2f903  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f908  ldarg.0
0x2f909  ldstr    aGrouproledefin// "GroupRoleDefinitionNamesLines"
0x2f90e  ldarg.3
0x2f90f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f914  ldarg.1
0x2f915  ldstr    aGrouproledefin// "GroupRoleDefinitionNamesLines"
0x2f91a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f91f  ldarg.3
0x2f920  ldstr    aGrouproledefin// "GroupRoleDefinitionNamesLines"
0x2f925  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f92a  ldarg.1
0x2f92b  ldloc.0
0x2f92c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_GroupRoleDefinitionNamesLines()
0x2f931  ldarg.3
0x2f932  call     T0x2B000114
0x2f937  ldarg.3
0x2f938  ldstr    aGrouproledefin// "GroupRoleDefinitionNamesLines"
0x2f93d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f942  ldarg.0
0x2f943  ldstr    aIsmobileview// "IsMobileView"
0x2f948  ldarg.3
0x2f949  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f94e  ldarg.1
0x2f94f  ldstr    aIsmobileview// "IsMobileView"
0x2f954  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f959  ldarg.3
0x2f95a  ldstr    aIsmobileview// "IsMobileView"
0x2f95f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f964  ldarg.1
0x2f965  ldloc.0
0x2f966  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_IsMobileView()
0x2f96b  ldarg.3
0x2f96c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f971  ldarg.3
0x2f972  ldstr    aIsmobileview// "IsMobileView"
0x2f977  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f97c  ldarg.0
0x2f97d  ldstr    aPanelgivepermi// "PanelGivePermissionsVisible"
0x2f982  ldarg.3
0x2f983  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f988  ldarg.1
0x2f989  ldstr    aPanelgivepermi// "PanelGivePermissionsVisible"
0x2f98e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f993  ldarg.3
0x2f994  ldstr    aPanelgivepermi// "PanelGivePermissionsVisible"
0x2f999  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f99e  ldarg.1
0x2f99f  ldloc.0
0x2f9a0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_PanelGivePermissionsVisible()
0x2f9a5  ldarg.3
0x2f9a6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f9ab  ldarg.3
0x2f9ac  ldstr    aPanelgivepermi// "PanelGivePermissionsVisible"
0x2f9b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f9b6  ldarg.0
0x2f9b7  ldstr    aPanelshowhidem// "PanelShowHideMoreOptionsVisible"
0x2f9bc  ldarg.3
0x2f9bd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f9c2  ldarg.1
0x2f9c3  ldstr    aPanelshowhidem// "PanelShowHideMoreOptionsVisible"
0x2f9c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2f9cd  ldarg.3
0x2f9ce  ldstr    aPanelshowhidem// "PanelShowHideMoreOptionsVisible"
0x2f9d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2f9d8  ldarg.1
0x2f9d9  ldloc.0
0x2f9da  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_PanelShowHideMoreOptionsVisible()
0x2f9df  ldarg.3
0x2f9e0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f9e5  ldarg.3
0x2f9e6  ldstr    aPanelshowhidem// "PanelShowHideMoreOptionsVisible"
0x2f9eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2f9f0  ldarg.0
0x2f9f1  ldstr    aPanelsimplifie// "PanelSimplifiedRoleSelectorVisible"
0x2f9f6  ldarg.3
0x2f9f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2f9fc  ldarg.1
0x2f9fd  ldstr    aPanelsimplifie// "PanelSimplifiedRoleSelectorVisible"
0x2fa02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fa07  ldarg.3
0x2fa08  ldstr    aPanelsimplifie// "PanelSimplifiedRoleSelectorVisible"
0x2fa0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fa12  ldarg.1
0x2fa13  ldloc.0
0x2fa14  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_PanelSimplifiedRoleSelectorVisible()
0x2fa19  ldarg.3
0x2fa1a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fa1f  ldarg.3
0x2fa20  ldstr    aPanelsimplifie// "PanelSimplifiedRoleSelectorVisible"
0x2fa25  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fa2a  ldarg.0
0x2fa2b  ldstr    aRequiredscript// "RequiredScriptFileLinks"
0x2fa30  ldarg.3
0x2fa31  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fa36  ldarg.1
0x2fa37  ldstr    aRequiredscript// "RequiredScriptFileLinks"
0x2fa3c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fa41  ldarg.3
0x2fa42  ldstr    aRequiredscript// "RequiredScriptFileLinks"
0x2fa47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fa4c  ldarg.1
0x2fa4d  ldloc.0
0x2fa4e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_RequiredScriptFileLinks()
0x2fa53  ldarg.3
0x2fa54  call     T0x2B000114
0x2fa59  ldarg.3
0x2fa5a  ldstr    aRequiredscript// "RequiredScriptFileLinks"
0x2fa5f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fa64  ldarg.0
0x2fa65  ldstr    aRoledefinition// "RoleDefinitionNameLines"
0x2fa6a  ldarg.3
0x2fa6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fa70  ldarg.1
0x2fa71  ldstr    aRoledefinition// "RoleDefinitionNameLines"
0x2fa76  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fa7b  ldarg.3
0x2fa7c  ldstr    aRoledefinition// "RoleDefinitionNameLines"
0x2fa81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fa86  ldarg.1
0x2fa87  ldloc.0
0x2fa88  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_RoleDefinitionNameLines()
0x2fa8d  ldarg.3
0x2fa8e  call     T0x2B000114
0x2fa93  ldarg.3
0x2fa94  ldstr    aRoledefinition// "RoleDefinitionNameLines"
0x2fa99  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fa9e  ldarg.0
0x2fa9f  ldstr    aSelectedgroup// "SelectedGroup"
0x2faa4  ldarg.3
0x2faa5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2faaa  ldarg.1
0x2faab  ldstr    aSelectedgroup// "SelectedGroup"
0x2fab0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fab5  ldarg.3
0x2fab6  ldstr    aSelectedgroup// "SelectedGroup"
0x2fabb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fac0  ldarg.1
0x2fac1  ldloc.0
0x2fac2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_SelectedGroup()
0x2fac7  ldarg.3
0x2fac8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2facd  ldarg.3
0x2face  ldstr    aSelectedgroup// "SelectedGroup"
0x2fad3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fad8  ldarg.0
0x2fad9  ldstr    aSharedwithenab// "SharedWithEnabled"
0x2fade  ldarg.3
0x2fadf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fae4  ldarg.1
0x2fae5  ldstr    aSharedwithenab// "SharedWithEnabled"
0x2faea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2faef  ldarg.3
0x2faf0  ldstr    aSharedwithenab// "SharedWithEnabled"
0x2faf5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fafa  ldarg.1
0x2fafb  ldloc.0
0x2fafc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_SharedWithEnabled()
0x2fb01  ldarg.3
0x2fb02  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb07  ldarg.3
0x2fb08  ldstr    aSharedwithenab// "SharedWithEnabled"
0x2fb0d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fb12  ldarg.0
0x2fb13  ldstr    aSharingcsslink// "SharingCssLink"
0x2fb18  ldarg.3
0x2fb19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb1e  ldarg.1
0x2fb1f  ldstr    aSharingcsslink// "SharingCssLink"
0x2fb24  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fb29  ldarg.3
0x2fb2a  ldstr    aSharingcsslink// "SharingCssLink"
0x2fb2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fb34  ldarg.1
0x2fb35  ldloc.0
0x2fb36  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_SharingCssLink()
0x2fb3b  ldarg.3
0x2fb3c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb41  ldarg.3
0x2fb42  ldstr    aSharingcsslink// "SharingCssLink"
0x2fb47  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fb4c  ldarg.0
0x2fb4d  ldstr    aTabbeddialogen// "TabbedDialogEnabled"
0x2fb52  ldarg.3
0x2fb53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb58  ldarg.1
0x2fb59  ldstr    aTabbeddialogen// "TabbedDialogEnabled"
0x2fb5e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fb63  ldarg.3
0x2fb64  ldstr    aTabbeddialogen// "TabbedDialogEnabled"
0x2fb69  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fb6e  ldarg.1
0x2fb6f  ldloc.0
0x2fb70  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_TabbedDialogEnabled()
0x2fb75  ldarg.3
0x2fb76  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb7b  ldarg.3
0x2fb7c  ldstr    aTabbeddialogen// "TabbedDialogEnabled"
0x2fb81  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fb86  ldarg.0
0x2fb87  ldstr    aTabtoshow// "TabToShow"
0x2fb8c  ldarg.3
0x2fb8d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fb92  ldarg.1
0x2fb93  ldstr    aTabtoshow// "TabToShow"
0x2fb98  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fb9d  ldarg.3
0x2fb9e  ldstr    aTabtoshow// "TabToShow"
0x2fba3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fba8  ldarg.1
0x2fba9  ldloc.0
0x2fbaa  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_TabToShow()
0x2fbaf  ldarg.3
0x2fbb0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fbb5  ldarg.3
0x2fbb6  ldstr    aTabtoshow// "TabToShow"
0x2fbbb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fbc0  ldarg.0
0x2fbc1  ldstr    aTxtemailsubjec// "txtEmailSubjectText"
0x2fbc6  ldarg.3
0x2fbc7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fbcc  ldarg.1
0x2fbcd  ldstr    aTxtemailsubjec// "txtEmailSubjectText"
0x2fbd2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fbd7  ldarg.3
0x2fbd8  ldstr    aTxtemailsubjec// "txtEmailSubjectText"
0x2fbdd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fbe2  ldarg.1
0x2fbe3  ldloc.0
0x2fbe4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_txtEmailSubjectText()
0x2fbe9  ldarg.3
0x2fbea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fbef  ldarg.3
0x2fbf0  ldstr    aTxtemailsubjec// "txtEmailSubjectText"
0x2fbf5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fbfa  ldarg.0
0x2fbfb  ldstr    aUserdisplayurl// "UserDisplayUrl"
0x2fc00  ldarg.3
0x2fc01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fc06  ldarg.1
0x2fc07  ldstr    aUserdisplayurl// "UserDisplayUrl"
0x2fc0c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2fc11  ldarg.3
0x2fc12  ldstr    aUserdisplayurl// "UserDisplayUrl"
0x2fc17  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2fc1c  ldarg.1
0x2fc1d  ldloc.0
0x2fc1e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharePointSharingSettings::get_UserDisplayUrl()
0x2fc23  ldarg.3
0x2fc24  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2fc29  ldarg.3
0x2fc2a  ldstr    aUserdisplayurl// "UserDisplayUrl"
0x2fc2f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2fc34  ret
  ... truncated ...
```
