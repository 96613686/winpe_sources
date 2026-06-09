# Microsoft.SharePoint.Sharing.SharingInformationServerStub::WritePropertiesAsJson

- ea: `0xaf430`
- end: `0xaf893`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::WritePropertiesAsJson`
- size: `1123`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xaf430`

## string_xrefs

- `0xaf445`: `anonymousLinkExpirationRestrictionDays`
- `0xaf451`: `anonymousLinkExpirationRestrictionDays`
- `0xaf45c`: `anonymousLinkExpirationRestrictionDays`
- `0xaf474`: `anonymousLinkExpirationRestrictionDays`
- `0xaf52d`: `canRequestAccessForGrantAccess`
- `0xaf539`: `canRequestAccessForGrantAccess`
- `0xaf544`: `canRequestAccessForGrantAccess`
- `0xaf55c`: `canRequestAccessForGrantAccess`
- `0xaf615`: `defaultLinkKind`
- `0xaf621`: `defaultLinkKind`
- `0xaf62c`: `defaultLinkKind`
- `0xaf644`: `defaultLinkKind`
- `0xaf64f`: `defaultShareLinkPermission`
- `0xaf65b`: `defaultShareLinkPermission`
- `0xaf666`: `defaultShareLinkPermission`
- `0xaf67e`: `defaultShareLinkPermission`
- `0xaf6fd`: `microserviceShareUiUrl`
- `0xaf709`: `microserviceShareUiUrl`
- `0xaf714`: `microserviceShareUiUrl`
- `0xaf72c`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xaf430  ldarg.2
0xaf431  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation
0xaf436  stloc.0
0xaf437  ldloc.0
0xaf438  brtrue.s loc_AF43B
0xaf43a  ret
0xaf43b  ldarg.0
0xaf43c  ldarg.1
0xaf43d  ldarg.2
0xaf43e  ldarg.3
0xaf43f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf444  ldarg.0
0xaf445  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaf44a  ldarg.3
0xaf44b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf450  ldarg.1
0xaf451  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaf456  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf45b  ldarg.3
0xaf45c  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaf461  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf466  ldarg.1
0xaf467  ldloc.0
0xaf468  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_AnonymousLinkExpirationRestrictionDays()
0xaf46d  ldarg.3
0xaf46e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf473  ldarg.3
0xaf474  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaf479  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf47e  ldarg.0
0xaf47f  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaf484  ldarg.3
0xaf485  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf48a  ldarg.1
0xaf48b  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaf490  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf495  ldarg.3
0xaf496  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaf49b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf4a0  ldarg.1
0xaf4a1  ldloc.0
0xaf4a2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_BlockPeoplePickerAndSharing()
0xaf4a7  ldarg.3
0xaf4a8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf4ad  ldarg.3
0xaf4ae  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaf4b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf4b8  ldarg.0
0xaf4b9  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaf4be  ldarg.3
0xaf4bf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf4c4  ldarg.1
0xaf4c5  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaf4ca  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf4cf  ldarg.3
0xaf4d0  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaf4d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf4da  ldarg.1
0xaf4db  ldloc.0
0xaf4dc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddExternalPrincipal()
0xaf4e1  ldarg.3
0xaf4e2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf4e7  ldarg.3
0xaf4e8  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaf4ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf4f2  ldarg.0
0xaf4f3  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaf4f8  ldarg.3
0xaf4f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf4fe  ldarg.1
0xaf4ff  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaf504  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf509  ldarg.3
0xaf50a  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaf50f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf514  ldarg.1
0xaf515  ldloc.0
0xaf516  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddInternalPrincipal()
0xaf51b  ldarg.3
0xaf51c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf521  ldarg.3
0xaf522  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaf527  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf52c  ldarg.0
0xaf52d  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaf532  ldarg.3
0xaf533  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf538  ldarg.1
0xaf539  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaf53e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf543  ldarg.3
0xaf544  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaf549  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf54e  ldarg.1
0xaf54f  ldloc.0
0xaf550  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanRequestAccessForGrantAccess()
0xaf555  ldarg.3
0xaf556  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf55b  ldarg.3
0xaf55c  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaf561  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf566  ldarg.0
0xaf567  ldstr    aCansendemail_0// "canSendEmail"
0xaf56c  ldarg.3
0xaf56d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf572  ldarg.1
0xaf573  ldstr    aCansendemail_0// "canSendEmail"
0xaf578  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf57d  ldarg.3
0xaf57e  ldstr    aCansendemail_0// "canSendEmail"
0xaf583  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf588  ldarg.1
0xaf589  ldloc.0
0xaf58a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanSendEmail()
0xaf58f  ldarg.3
0xaf590  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf595  ldarg.3
0xaf596  ldstr    aCansendemail_0// "canSendEmail"
0xaf59b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf5a0  ldarg.0
0xaf5a1  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaf5a6  ldarg.3
0xaf5a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf5ac  ldarg.1
0xaf5ad  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaf5b2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf5b7  ldarg.3
0xaf5b8  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaf5bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf5c2  ldarg.1
0xaf5c3  ldloc.0
0xaf5c4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanUseSimplifiedRoles()
0xaf5c9  ldarg.3
0xaf5ca  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf5cf  ldarg.3
0xaf5d0  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaf5d5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf5da  ldarg.0
0xaf5db  ldstr    aCurrentrole// "currentRole"
0xaf5e0  ldarg.3
0xaf5e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf5e6  ldarg.1
0xaf5e7  ldstr    aCurrentrole// "currentRole"
0xaf5ec  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf5f1  ldarg.3
0xaf5f2  ldstr    aCurrentrole// "currentRole"
0xaf5f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf5fc  ldarg.1
0xaf5fd  ldloc.0
0xaf5fe  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CurrentRole()
0xaf603  ldarg.3
0xaf604  call     T0x2B000111
0xaf609  ldarg.3
0xaf60a  ldstr    aCurrentrole// "currentRole"
0xaf60f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf614  ldarg.0
0xaf615  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaf61a  ldarg.3
0xaf61b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf620  ldarg.1
0xaf621  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaf626  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf62b  ldarg.3
0xaf62c  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaf631  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf636  ldarg.1
0xaf637  ldloc.0
0xaf638  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DefaultLinkKind()
0xaf63d  ldarg.3
0xaf63e  call     T0x2B000112
0xaf643  ldarg.3
0xaf644  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaf649  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf64e  ldarg.0
0xaf64f  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaf654  ldarg.3
0xaf655  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf65a  ldarg.1
0xaf65b  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaf660  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf665  ldarg.3
0xaf666  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaf66b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf670  ldarg.1
0xaf671  ldloc.0
0xaf672  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DefaultShareLinkPermission()
0xaf677  ldarg.3
0xaf678  call     T0x2B000111
0xaf67d  ldarg.3
0xaf67e  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaf683  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf688  ldarg.0
0xaf689  ldstr    aDirecturl// "directUrl"
0xaf68e  ldarg.3
0xaf68f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf694  ldarg.1
0xaf695  ldstr    aDirecturl// "directUrl"
0xaf69a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf69f  ldarg.3
0xaf6a0  ldstr    aDirecturl// "directUrl"
0xaf6a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf6aa  ldarg.1
0xaf6ab  ldloc.0
0xaf6ac  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_DirectUrl()
0xaf6b1  ldarg.3
0xaf6b2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf6b7  ldarg.3
0xaf6b8  ldstr    aDirecturl// "directUrl"
0xaf6bd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf6c2  ldarg.0
0xaf6c3  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaf6c8  ldarg.3
0xaf6c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf6ce  ldarg.1
0xaf6cf  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaf6d4  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf6d9  ldarg.3
0xaf6da  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaf6df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf6e4  ldarg.1
0xaf6e5  ldloc.0
0xaf6e6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_HasUniquePermissions()
0xaf6eb  ldarg.3
0xaf6ec  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf6f1  ldarg.3
0xaf6f2  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaf6f7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf6fc  ldarg.0
0xaf6fd  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaf702  ldarg.3
0xaf703  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf708  ldarg.1
0xaf709  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaf70e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf713  ldarg.3
0xaf714  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaf719  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf71e  ldarg.1
0xaf71f  ldloc.0
0xaf720  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_MicroserviceShareUiUrl()
0xaf725  ldarg.3
0xaf726  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf72b  ldarg.3
0xaf72c  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaf731  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf736  ldarg.0
0xaf737  ldstr    aSharedobjectty// "sharedObjectType"
0xaf73c  ldarg.3
0xaf73d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf742  ldarg.1
0xaf743  ldstr    aSharedobjectty// "sharedObjectType"
0xaf748  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf74d  ldarg.3
0xaf74e  ldstr    aSharedobjectty// "sharedObjectType"
0xaf753  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf758  ldarg.1
0xaf759  ldloc.0
0xaf75a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SPSharedObjectType [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_SharedObjectType()
0xaf75f  ldarg.3
0xaf760  call     T0x2B000119
0xaf765  ldarg.3
0xaf766  ldstr    aSharedobjectty// "sharedObjectType"
0xaf76b  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf770  ldarg.0
0xaf771  ldstr    aShareuiurl// "shareUiUrl"
0xaf776  ldarg.3
0xaf777  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf77c  ldarg.1
0xaf77d  ldstr    aShareuiurl// "shareUiUrl"
0xaf782  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf787  ldarg.3
0xaf788  ldstr    aShareuiurl// "shareUiUrl"
0xaf78d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf792  ldarg.1
0xaf793  ldloc.0
0xaf794  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_ShareUiUrl()
0xaf799  ldarg.3
0xaf79a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf79f  ldarg.3
0xaf7a0  ldstr    aShareuiurl// "shareUiUrl"
0xaf7a5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf7aa  ldarg.0
0xaf7ab  ldstr    aSharingabiliti// "sharingAbilities"
0xaf7b0  ldarg.3
0xaf7b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf7b6  ldarg.1
0xaf7b7  ldstr    aSharingabiliti// "sharingAbilities"
0xaf7bc  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0xaf7c1  ldarg.3
0xaf7c2  ldstr    aSharingabiliti// "sharingAbilities"
0xaf7c7  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0xaf7cc  ldarg.1
0xaf7cd  ldloc.0
0xaf7ce  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilities [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_SharingAbilities()
0xaf7d3  ldarg.3
0xaf7d4  call     T0x2B0002A3
0xaf7d9  ldarg.3
0xaf7da  ldstr    aSharingabiliti// "sharingAbilities"
0xaf7df  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0xaf7e4  ldarg.0
  ... truncated ...
```
