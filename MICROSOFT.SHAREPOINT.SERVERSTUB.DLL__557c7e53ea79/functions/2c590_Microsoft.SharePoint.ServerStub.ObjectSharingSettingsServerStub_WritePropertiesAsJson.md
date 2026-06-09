# Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::WritePropertiesAsJson

- ea: `0x2c590`
- end: `0x2cdcd`
- name: `Microsoft.SharePoint.ServerStub.ObjectSharingSettingsServerStub::WritePropertiesAsJson`
- size: `2109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x2c590`

## string_xrefs

- `0x2c5a5`: `AccessRequestMode`
- `0x2c5b1`: `AccessRequestMode`
- `0x2c5bc`: `AccessRequestMode`
- `0x2c5d4`: `AccessRequestMode`
- `0x2c619`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2c625`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2c630`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2c648`: `CanCurrentUserManageOrganizationReadonlyLink`
- `0x2c653`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2c65f`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2c66a`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2c682`: `CanCurrentUserManageOrganizationReadWriteLink`
- `0x2c68d`: `CanCurrentUserManageReadonlyLink`
- `0x2c699`: `CanCurrentUserManageReadonlyLink`
- `0x2c6a4`: `CanCurrentUserManageReadonlyLink`
- `0x2c6bc`: `CanCurrentUserManageReadonlyLink`
- `0x2c6c7`: `CanCurrentUserManageReadWriteLink`
- `0x2c6d3`: `CanCurrentUserManageReadWriteLink`
- `0x2c6de`: `CanCurrentUserManageReadWriteLink`
- `0x2c6f6`: `CanCurrentUserManageReadWriteLink`
- `0x2c701`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2c70d`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2c718`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2c730`: `CanCurrentUserRetrieveOrganizationReadonlyLink`
- `0x2c73b`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2c747`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2c752`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2c76a`: `CanCurrentUserRetrieveOrganizationReadWriteLink`
- `0x2c775`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2c781`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2c78c`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2c7a4`: `CanCurrentUserRetrieveReadonlyLink`
- `0x2c7af`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2c7bb`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2c7c6`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2c7de`: `CanCurrentUserRetrieveReadWriteLink`
- `0x2c897`: `CanSendLink`
- `0x2c8a3`: `CanSendLink`
- `0x2c8ae`: `CanSendLink`
- `0x2c8c6`: `CanSendLink`
- `0x2c90b`: `DefaultShareLinkPermission`
- `0x2c917`: `DefaultShareLinkPermission`
- `0x2c922`: `DefaultShareLinkPermission`
- `0x2c93a`: `DefaultShareLinkPermission`
- `0x2c945`: `DefaultShareLinkType`
- `0x2c951`: `DefaultShareLinkType`
- `0x2c95c`: `DefaultShareLinkType`
- `0x2c974`: `DefaultShareLinkType`
- `0x2c9f3`: `HasReadRole`
- `0x2c9ff`: `HasReadRole`
- `0x2ca0a`: `HasReadRole`
- `0x2ca22`: `HasReadRole`
- `0x2ca2d`: `InheritingWebLink`
- `0x2ca39`: `InheritingWebLink`
- `0x2ca44`: `InheritingWebLink`
- `0x2ca5c`: `InheritingWebLink`
- `0x2cc37`: `RequiredAnonymousLinkExpirationInDays`
- `0x2cc43`: `RequiredAnonymousLinkExpirationInDays`
- `0x2cc4e`: `RequiredAnonymousLinkExpirationInDays`
- `0x2cc66`: `RequiredAnonymousLinkExpirationInDays`
- `0x2cd59`: `SupportsAclPropagation`
- `0x2cd65`: `SupportsAclPropagation`
- `0x2cd70`: `SupportsAclPropagation`
- `0x2cd88`: `SupportsAclPropagation`

## pseudocode

```c

```

## disassembly

```asm
0x2c590  ldarg.2
0x2c591  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings
0x2c596  stloc.0
0x2c597  ldloc.0
0x2c598  brtrue.s loc_2C59B
0x2c59a  ret
0x2c59b  ldarg.0
0x2c59c  ldarg.1
0x2c59d  ldarg.2
0x2c59e  ldarg.3
0x2c59f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c5a4  ldarg.0
0x2c5a5  ldstr    aAccessrequestm// "AccessRequestMode"
0x2c5aa  ldarg.3
0x2c5ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c5b0  ldarg.1
0x2c5b1  ldstr    aAccessrequestm// "AccessRequestMode"
0x2c5b6  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c5bb  ldarg.3
0x2c5bc  ldstr    aAccessrequestm// "AccessRequestMode"
0x2c5c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c5c6  ldarg.1
0x2c5c7  ldloc.0
0x2c5c8  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_AccessRequestMode()
0x2c5cd  ldarg.3
0x2c5ce  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c5d3  ldarg.3
0x2c5d4  ldstr    aAccessrequestm// "AccessRequestMode"
0x2c5d9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c5de  ldarg.0
0x2c5df  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2c5e4  ldarg.3
0x2c5e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c5ea  ldarg.1
0x2c5eb  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2c5f0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c5f5  ldarg.3
0x2c5f6  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2c5fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c600  ldarg.1
0x2c601  ldloc.0
0x2c602  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_BlockPeoplePickerAndSharing()
0x2c607  ldarg.3
0x2c608  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c60d  ldarg.3
0x2c60e  ldstr    aBlockpeoplepic// "BlockPeoplePickerAndSharing"
0x2c613  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c618  ldarg.0
0x2c619  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2c61e  ldarg.3
0x2c61f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c624  ldarg.1
0x2c625  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2c62a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c62f  ldarg.3
0x2c630  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2c635  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c63a  ldarg.1
0x2c63b  ldloc.0
0x2c63c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadonlyLink()
0x2c641  ldarg.3
0x2c642  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c647  ldarg.3
0x2c648  ldstr    aCancurrentuser// "CanCurrentUserManageOrganizationReadonl"...
0x2c64d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c652  ldarg.0
0x2c653  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2c658  ldarg.3
0x2c659  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c65e  ldarg.1
0x2c65f  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2c664  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c669  ldarg.3
0x2c66a  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2c66f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c674  ldarg.1
0x2c675  ldloc.0
0x2c676  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageOrganizationReadWriteLink()
0x2c67b  ldarg.3
0x2c67c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c681  ldarg.3
0x2c682  ldstr    aCancurrentuser_0// "CanCurrentUserManageOrganizationReadWri"...
0x2c687  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c68c  ldarg.0
0x2c68d  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2c692  ldarg.3
0x2c693  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c698  ldarg.1
0x2c699  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2c69e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c6a3  ldarg.3
0x2c6a4  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2c6a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c6ae  ldarg.1
0x2c6af  ldloc.0
0x2c6b0  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageReadonlyLink()
0x2c6b5  ldarg.3
0x2c6b6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c6bb  ldarg.3
0x2c6bc  ldstr    aCancurrentuser_1// "CanCurrentUserManageReadonlyLink"
0x2c6c1  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c6c6  ldarg.0
0x2c6c7  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2c6cc  ldarg.3
0x2c6cd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c6d2  ldarg.1
0x2c6d3  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2c6d8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c6dd  ldarg.3
0x2c6de  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2c6e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c6e8  ldarg.1
0x2c6e9  ldloc.0
0x2c6ea  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserManageReadWriteLink()
0x2c6ef  ldarg.3
0x2c6f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c6f5  ldarg.3
0x2c6f6  ldstr    aCancurrentuser_2// "CanCurrentUserManageReadWriteLink"
0x2c6fb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c700  ldarg.0
0x2c701  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2c706  ldarg.3
0x2c707  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c70c  ldarg.1
0x2c70d  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2c712  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c717  ldarg.3
0x2c718  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2c71d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c722  ldarg.1
0x2c723  ldloc.0
0x2c724  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveOrganizationReadonlyLink()
0x2c729  ldarg.3
0x2c72a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c72f  ldarg.3
0x2c730  ldstr    aCancurrentuser_3// "CanCurrentUserRetrieveOrganizationReado"...
0x2c735  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c73a  ldarg.0
0x2c73b  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2c740  ldarg.3
0x2c741  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c746  ldarg.1
0x2c747  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2c74c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c751  ldarg.3
0x2c752  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2c757  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c75c  ldarg.1
0x2c75d  ldloc.0
0x2c75e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveOrganizationReadWriteLink()
0x2c763  ldarg.3
0x2c764  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c769  ldarg.3
0x2c76a  ldstr    aCancurrentuser_4// "CanCurrentUserRetrieveOrganizationReadW"...
0x2c76f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c774  ldarg.0
0x2c775  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2c77a  ldarg.3
0x2c77b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c780  ldarg.1
0x2c781  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2c786  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c78b  ldarg.3
0x2c78c  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2c791  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c796  ldarg.1
0x2c797  ldloc.0
0x2c798  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveReadonlyLink()
0x2c79d  ldarg.3
0x2c79e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c7a3  ldarg.3
0x2c7a4  ldstr    aCancurrentuser_5// "CanCurrentUserRetrieveReadonlyLink"
0x2c7a9  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c7ae  ldarg.0
0x2c7af  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2c7b4  ldarg.3
0x2c7b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c7ba  ldarg.1
0x2c7bb  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2c7c0  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c7c5  ldarg.3
0x2c7c6  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2c7cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c7d0  ldarg.1
0x2c7d1  ldloc.0
0x2c7d2  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserRetrieveReadWriteLink()
0x2c7d7  ldarg.3
0x2c7d8  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c7dd  ldarg.3
0x2c7de  ldstr    aCancurrentuser_6// "CanCurrentUserRetrieveReadWriteLink"
0x2c7e3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c7e8  ldarg.0
0x2c7e9  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2c7ee  ldarg.3
0x2c7ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c7f4  ldarg.1
0x2c7f5  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2c7fa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c7ff  ldarg.3
0x2c800  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2c805  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c80a  ldarg.1
0x2c80b  ldloc.0
0x2c80c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserShareExternally()
0x2c811  ldarg.3
0x2c812  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c817  ldarg.3
0x2c818  ldstr    aCancurrentuser_7// "CanCurrentUserShareExternally"
0x2c81d  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c822  ldarg.0
0x2c823  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2c828  ldarg.3
0x2c829  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c82e  ldarg.1
0x2c82f  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2c834  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c839  ldarg.3
0x2c83a  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2c83f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c844  ldarg.1
0x2c845  ldloc.0
0x2c846  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanCurrentUserShareInternally()
0x2c84b  ldarg.3
0x2c84c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c851  ldarg.3
0x2c852  ldstr    aCancurrentuser_8// "CanCurrentUserShareInternally"
0x2c857  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c85c  ldarg.0
0x2c85d  ldstr    aCansendemail// "CanSendEmail"
0x2c862  ldarg.3
0x2c863  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c868  ldarg.1
0x2c869  ldstr    aCansendemail// "CanSendEmail"
0x2c86e  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c873  ldarg.3
0x2c874  ldstr    aCansendemail// "CanSendEmail"
0x2c879  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c87e  ldarg.1
0x2c87f  ldloc.0
0x2c880  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanSendEmail()
0x2c885  ldarg.3
0x2c886  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c88b  ldarg.3
0x2c88c  ldstr    aCansendemail// "CanSendEmail"
0x2c891  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c896  ldarg.0
0x2c897  ldstr    aCansendlink// "CanSendLink"
0x2c89c  ldarg.3
0x2c89d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c8a2  ldarg.1
0x2c8a3  ldstr    aCansendlink// "CanSendLink"
0x2c8a8  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c8ad  ldarg.3
0x2c8ae  ldstr    aCansendlink// "CanSendLink"
0x2c8b3  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c8b8  ldarg.1
0x2c8b9  ldloc.0
0x2c8ba  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanSendLink()
0x2c8bf  ldarg.3
0x2c8c0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c8c5  ldarg.3
0x2c8c6  ldstr    aCansendlink// "CanSendLink"
0x2c8cb  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c8d0  ldarg.0
0x2c8d1  ldstr    aCansharefolder// "CanShareFolder"
0x2c8d6  ldarg.3
0x2c8d7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c8dc  ldarg.1
0x2c8dd  ldstr    aCansharefolder// "CanShareFolder"
0x2c8e2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c8e7  ldarg.3
0x2c8e8  ldstr    aCansharefolder// "CanShareFolder"
0x2c8ed  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c8f2  ldarg.1
0x2c8f3  ldloc.0
0x2c8f4  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_CanShareFolder()
0x2c8f9  ldarg.3
0x2c8fa  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c8ff  ldarg.3
0x2c900  ldstr    aCansharefolder// "CanShareFolder"
0x2c905  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c90a  ldarg.0
0x2c90b  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2c910  ldarg.3
0x2c911  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2c916  ldarg.1
0x2c917  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2c91c  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x2c921  ldarg.3
0x2c922  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2c927  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::BeginPerformanceMarker(string)
0x2c92c  ldarg.1
0x2c92d  ldloc.0
0x2c92e  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings::get_DefaultShareLinkPermission()
0x2c933  ldarg.3
0x2c934  call     T0x2B000111
0x2c939  ldarg.3
0x2c93a  ldstr    aDefaultshareli// "DefaultShareLinkPermission"
0x2c93f  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::EndPerformanceMarker(string)
0x2c944  ldarg.0
  ... truncated ...
```
