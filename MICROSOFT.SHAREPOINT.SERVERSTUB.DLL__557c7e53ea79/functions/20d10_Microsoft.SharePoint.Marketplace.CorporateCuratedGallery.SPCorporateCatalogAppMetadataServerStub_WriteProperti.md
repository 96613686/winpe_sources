# Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::WritePropertiesAsJson

- ea: `0x20d10`
- end: `0x20ef5`
- name: `Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadataServerStub::WritePropertiesAsJson`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x20d10`

## string_xrefs

- `0x20e47`: `InstalledVersion`
- `0x20e53`: `InstalledVersion`
- `0x20e5e`: `InstalledVersion`
- `0x20e76`: `InstalledVersion`
- `0x20e81`: `IsClientSideSolution`
- `0x20e8d`: `IsClientSideSolution`
- `0x20e98`: `IsClientSideSolution`
- `0x20eb0`: `IsClientSideSolution`

## pseudocode

```c

```

## disassembly

```asm
0x20d10  ldarg.2
0x20d11  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata
0x20d16  stloc.0
0x20d17  ldloc.0
0x20d18  brtrue.s loc_20D1B
0x20d1a  ret
0x20d1b  ldarg.0
0x20d1c  ldarg.1
0x20d1d  ldarg.2
0x20d1e  ldarg.3
0x20d1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20d24  ldarg.0
0x20d25  ldstr    aAppcatalogvers// "AppCatalogVersion"
0x20d2a  ldarg.3
0x20d2b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20d30  ldarg.1
0x20d31  ldstr    aAppcatalogvers// "AppCatalogVersion"
0x20d36  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20d3b  ldarg.3
0x20d3c  ldstr    aAppcatalogvers// "AppCatalogVersion"
0x20d41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20d46  ldarg.1
0x20d47  ldloc.0
0x20d48  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_AppCatalogVersion()
0x20d4d  ldarg.3
0x20d4e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20d53  ldarg.3
0x20d54  ldstr    aAppcatalogvers// "AppCatalogVersion"
0x20d59  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20d5e  ldarg.0
0x20d5f  ldstr    aCanupgrade// "CanUpgrade"
0x20d64  ldarg.3
0x20d65  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20d6a  ldarg.1
0x20d6b  ldstr    aCanupgrade// "CanUpgrade"
0x20d70  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20d75  ldarg.3
0x20d76  ldstr    aCanupgrade// "CanUpgrade"
0x20d7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20d80  ldarg.1
0x20d81  ldloc.0
0x20d82  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_CanUpgrade()
0x20d87  ldarg.3
0x20d88  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20d8d  ldarg.3
0x20d8e  ldstr    aCanupgrade// "CanUpgrade"
0x20d93  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20d98  ldarg.0
0x20d99  ldstr    aCurrentversion// "CurrentVersionDeployed"
0x20d9e  ldarg.3
0x20d9f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20da4  ldarg.1
0x20da5  ldstr    aCurrentversion// "CurrentVersionDeployed"
0x20daa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20daf  ldarg.3
0x20db0  ldstr    aCurrentversion// "CurrentVersionDeployed"
0x20db5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20dba  ldarg.1
0x20dbb  ldloc.0
0x20dbc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_CurrentVersionDeployed_Client()
0x20dc1  ldarg.3
0x20dc2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20dc7  ldarg.3
0x20dc8  ldstr    aCurrentversion// "CurrentVersionDeployed"
0x20dcd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20dd2  ldarg.0
0x20dd3  ldstr    aDeployed// "Deployed"
0x20dd8  ldarg.3
0x20dd9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20dde  ldarg.1
0x20ddf  ldstr    aDeployed// "Deployed"
0x20de4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20de9  ldarg.3
0x20dea  ldstr    aDeployed// "Deployed"
0x20def  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20df4  ldarg.1
0x20df5  ldloc.0
0x20df6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_Deployed_Client()
0x20dfb  ldarg.3
0x20dfc  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e01  ldarg.3
0x20e02  ldstr    aDeployed// "Deployed"
0x20e07  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20e0c  ldarg.0
0x20e0d  ldstr    aId_1// "ID"
0x20e12  ldarg.3
0x20e13  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e18  ldarg.1
0x20e19  ldstr    aId_1// "ID"
0x20e1e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20e23  ldarg.3
0x20e24  ldstr    aId_1// "ID"
0x20e29  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20e2e  ldarg.1
0x20e2f  ldloc.0
0x20e30  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_ID_Client()
0x20e35  ldarg.3
0x20e36  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e3b  ldarg.3
0x20e3c  ldstr    aId_1// "ID"
0x20e41  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20e46  ldarg.0
0x20e47  ldstr    aInstalledversi// "InstalledVersion"
0x20e4c  ldarg.3
0x20e4d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e52  ldarg.1
0x20e53  ldstr    aInstalledversi// "InstalledVersion"
0x20e58  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20e5d  ldarg.3
0x20e5e  ldstr    aInstalledversi// "InstalledVersion"
0x20e63  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20e68  ldarg.1
0x20e69  ldloc.0
0x20e6a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_InstalledVersion()
0x20e6f  ldarg.3
0x20e70  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e75  ldarg.3
0x20e76  ldstr    aInstalledversi// "InstalledVersion"
0x20e7b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20e80  ldarg.0
0x20e81  ldstr    aIsclientsideso// "IsClientSideSolution"
0x20e86  ldarg.3
0x20e87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20e8c  ldarg.1
0x20e8d  ldstr    aIsclientsideso// "IsClientSideSolution"
0x20e92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20e97  ldarg.3
0x20e98  ldstr    aIsclientsideso// "IsClientSideSolution"
0x20e9d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20ea2  ldarg.1
0x20ea3  ldloc.0
0x20ea4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_IsClientSideSolution_Client()
0x20ea9  ldarg.3
0x20eaa  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20eaf  ldarg.3
0x20eb0  ldstr    aIsclientsideso// "IsClientSideSolution"
0x20eb5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20eba  ldarg.0
0x20ebb  ldstr    aTitle// "Title"
0x20ec0  ldarg.3
0x20ec1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20ec6  ldarg.1
0x20ec7  ldstr    aTitle// "Title"
0x20ecc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x20ed1  ldarg.3
0x20ed2  ldstr    aTitle// "Title"
0x20ed7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x20edc  ldarg.1
0x20edd  ldloc.0
0x20ede  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAppMetadata::get_Title_Client()
0x20ee3  ldarg.3
0x20ee4  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x20ee9  ldarg.3
0x20eea  ldstr    aTitle// "Title"
0x20eef  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x20ef4  ret
```
