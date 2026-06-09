# Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::WritePropertiesAsJson

- ea: `0x6e280`
- end: `0x6e5fb`
- name: `Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::WritePropertiesAsJson`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6e280`

## string_xrefs

- `0x6e295`: `AnonymousEditLink`
- `0x6e2a1`: `AnonymousEditLink`
- `0x6e2ac`: `AnonymousEditLink`
- `0x6e2c4`: `AnonymousEditLink`
- `0x6e2cf`: `AnonymousViewLink`
- `0x6e2db`: `AnonymousViewLink`
- `0x6e2e6`: `AnonymousViewLink`
- `0x6e2fe`: `AnonymousViewLink`
- `0x6e3b7`: `HasPendingAccessRequests`
- `0x6e3c3`: `HasPendingAccessRequests`
- `0x6e3ce`: `HasPendingAccessRequests`
- `0x6e3e6`: `HasPendingAccessRequests`
- `0x6e513`: `IsSharedWithSecurityGroup`
- `0x6e51f`: `IsSharedWithSecurityGroup`
- `0x6e52a`: `IsSharedWithSecurityGroup`
- `0x6e542`: `IsSharedWithSecurityGroup`
- `0x6e54d`: `PendingAccessRequestsLink`
- `0x6e559`: `PendingAccessRequestsLink`
- `0x6e564`: `PendingAccessRequestsLink`
- `0x6e57c`: `PendingAccessRequestsLink`
- `0x6e587`: `SharingLinks`
- `0x6e593`: `SharingLinks`
- `0x6e59e`: `SharingLinks`
- `0x6e5b6`: `SharingLinks`

## pseudocode

```c

```

## disassembly

```asm
0x6e280  ldarg.2
0x6e281  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation
0x6e286  stloc.0
0x6e287  ldloc.0
0x6e288  brtrue.s loc_6E28B
0x6e28a  ret
0x6e28b  ldarg.0
0x6e28c  ldarg.1
0x6e28d  ldarg.2
0x6e28e  ldarg.3
0x6e28f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e294  ldarg.0
0x6e295  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6e29a  ldarg.3
0x6e29b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e2a0  ldarg.1
0x6e2a1  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6e2a6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e2ab  ldarg.3
0x6e2ac  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6e2b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e2b6  ldarg.1
0x6e2b7  ldloc.0
0x6e2b8  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousEditLink()
0x6e2bd  ldarg.3
0x6e2be  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e2c3  ldarg.3
0x6e2c4  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6e2c9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e2ce  ldarg.0
0x6e2cf  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6e2d4  ldarg.3
0x6e2d5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e2da  ldarg.1
0x6e2db  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6e2e0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e2e5  ldarg.3
0x6e2e6  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6e2eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e2f0  ldarg.1
0x6e2f1  ldloc.0
0x6e2f2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousViewLink()
0x6e2f7  ldarg.3
0x6e2f8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e2fd  ldarg.3
0x6e2fe  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6e303  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e308  ldarg.0
0x6e309  ldstr    aCanbeshared// "CanBeShared"
0x6e30e  ldarg.3
0x6e30f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e314  ldarg.1
0x6e315  ldstr    aCanbeshared// "CanBeShared"
0x6e31a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e31f  ldarg.3
0x6e320  ldstr    aCanbeshared// "CanBeShared"
0x6e325  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e32a  ldarg.1
0x6e32b  ldloc.0
0x6e32c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeShared()
0x6e331  ldarg.3
0x6e332  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e337  ldarg.3
0x6e338  ldstr    aCanbeshared// "CanBeShared"
0x6e33d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e342  ldarg.0
0x6e343  ldstr    aCanbeunshared// "CanBeUnshared"
0x6e348  ldarg.3
0x6e349  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e34e  ldarg.1
0x6e34f  ldstr    aCanbeunshared// "CanBeUnshared"
0x6e354  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e359  ldarg.3
0x6e35a  ldstr    aCanbeunshared// "CanBeUnshared"
0x6e35f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e364  ldarg.1
0x6e365  ldloc.0
0x6e366  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeUnshared()
0x6e36b  ldarg.3
0x6e36c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e371  ldarg.3
0x6e372  ldstr    aCanbeunshared// "CanBeUnshared"
0x6e377  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e37c  ldarg.0
0x6e37d  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6e382  ldarg.3
0x6e383  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e388  ldarg.1
0x6e389  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6e38e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e393  ldarg.3
0x6e394  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6e399  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e39e  ldarg.1
0x6e39f  ldloc.0
0x6e3a0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanManagePermissions()
0x6e3a5  ldarg.3
0x6e3a6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e3ab  ldarg.3
0x6e3ac  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6e3b1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e3b6  ldarg.0
0x6e3b7  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6e3bc  ldarg.3
0x6e3bd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e3c2  ldarg.1
0x6e3c3  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6e3c8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e3cd  ldarg.3
0x6e3ce  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6e3d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e3d8  ldarg.1
0x6e3d9  ldloc.0
0x6e3da  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPendingAccessRequests()
0x6e3df  ldarg.3
0x6e3e0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e3e5  ldarg.3
0x6e3e6  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6e3eb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e3f0  ldarg.0
0x6e3f1  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6e3f6  ldarg.3
0x6e3f7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e3fc  ldarg.1
0x6e3fd  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6e402  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e407  ldarg.3
0x6e408  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6e40d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e412  ldarg.1
0x6e413  ldloc.0
0x6e414  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPermissionLevels()
0x6e419  ldarg.3
0x6e41a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e41f  ldarg.3
0x6e420  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6e425  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e42a  ldarg.0
0x6e42b  ldstr    aIsfolder// "IsFolder"
0x6e430  ldarg.3
0x6e431  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e436  ldarg.1
0x6e437  ldstr    aIsfolder// "IsFolder"
0x6e43c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e441  ldarg.3
0x6e442  ldstr    aIsfolder// "IsFolder"
0x6e447  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e44c  ldarg.1
0x6e44d  ldloc.0
0x6e44e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsFolder()
0x6e453  ldarg.3
0x6e454  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e459  ldarg.3
0x6e45a  ldstr    aIsfolder// "IsFolder"
0x6e45f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e464  ldarg.0
0x6e465  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6e46a  ldarg.3
0x6e46b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e470  ldarg.1
0x6e471  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6e476  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e47b  ldarg.3
0x6e47c  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6e481  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e486  ldarg.1
0x6e487  ldloc.0
0x6e488  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithCurrentUser()
0x6e48d  ldarg.3
0x6e48e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e493  ldarg.3
0x6e494  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6e499  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e49e  ldarg.0
0x6e49f  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6e4a4  ldarg.3
0x6e4a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e4aa  ldarg.1
0x6e4ab  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6e4b0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e4b5  ldarg.3
0x6e4b6  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6e4bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e4c0  ldarg.1
0x6e4c1  ldloc.0
0x6e4c2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithGuest()
0x6e4c7  ldarg.3
0x6e4c8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e4cd  ldarg.3
0x6e4ce  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6e4d3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e4d8  ldarg.0
0x6e4d9  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6e4de  ldarg.3
0x6e4df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e4e4  ldarg.1
0x6e4e5  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6e4ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e4ef  ldarg.3
0x6e4f0  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6e4f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e4fa  ldarg.1
0x6e4fb  ldloc.0
0x6e4fc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithMany()
0x6e501  ldarg.3
0x6e502  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e507  ldarg.3
0x6e508  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6e50d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e512  ldarg.0
0x6e513  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6e518  ldarg.3
0x6e519  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e51e  ldarg.1
0x6e51f  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6e524  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e529  ldarg.3
0x6e52a  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6e52f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e534  ldarg.1
0x6e535  ldloc.0
0x6e536  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithSecurityGroup()
0x6e53b  ldarg.3
0x6e53c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e541  ldarg.3
0x6e542  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6e547  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e54c  ldarg.0
0x6e54d  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6e552  ldarg.3
0x6e553  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e558  ldarg.1
0x6e559  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6e55e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e563  ldarg.3
0x6e564  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6e569  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e56e  ldarg.1
0x6e56f  ldloc.0
0x6e570  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_PendingAccessRequestsLink()
0x6e575  ldarg.3
0x6e576  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e57b  ldarg.3
0x6e57c  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6e581  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e586  ldarg.0
0x6e587  ldstr    aSharinglinks// "SharingLinks"
0x6e58c  ldarg.3
0x6e58d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e592  ldarg.1
0x6e593  ldstr    aSharinglinks// "SharingLinks"
0x6e598  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e59d  ldarg.3
0x6e59e  ldstr    aSharinglinks// "SharingLinks"
0x6e5a3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e5a8  ldarg.1
0x6e5a9  ldloc.0
0x6e5aa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo> [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_SharingLinks()
0x6e5af  ldarg.3
0x6e5b0  call     T0x2B0001E3
0x6e5b5  ldarg.3
0x6e5b6  ldstr    aSharinglinks// "SharingLinks"
0x6e5bb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e5c0  ldarg.0
0x6e5c1  ldstr    aTotalfilecount// "TotalFileCount"
0x6e5c6  ldarg.3
0x6e5c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e5cc  ldarg.1
0x6e5cd  ldstr    aTotalfilecount// "TotalFileCount"
0x6e5d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x6e5d7  ldarg.3
0x6e5d8  ldstr    aTotalfilecount// "TotalFileCount"
0x6e5dd  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x6e5e2  ldarg.1
0x6e5e3  ldloc.0
0x6e5e4  callvirt instance unsigned int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_TotalFileCount()
0x6e5e9  ldarg.3
0x6e5ea  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteUInt64(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, unsigned int64, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6e5ef  ldarg.3
0x6e5f0  ldstr    aTotalfilecount// "TotalFileCount"
0x6e5f5  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x6e5fa  ret
```
