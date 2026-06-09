# Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter::WritePropertiesAsJson

- ea: `0x309a0`
- end: `0x30b65`
- name: `Microsoft.SharePoint.ServerStub.SharingLinkInfoValueTypeConverter::WritePropertiesAsJson`
- size: `453`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x309a0`

## string_xrefs

- `0x309cd`: `Created`
- `0x30a75`: `IsFormsLink`
- `0x30a8d`: `IsReviewLink`
- `0x30aed`: `LinkKind`
- `0x309b5`: `AllowsAnonymousAccess`
- `0x309e5`: `CreatedBy`
- `0x30a5d`: `IsEditLink`

## pseudocode

```c

```

## disassembly

```asm
0x309a0  ldarg.2
0x309a1  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo
0x309a6  stloc.0
0x309a7  ldloc.0
0x309a8  brtrue.s loc_309AB
0x309aa  ret
0x309ab  ldarg.0
0x309ac  ldarg.1
0x309ad  ldarg.2
0x309ae  ldarg.3
0x309af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::WritePropertiesAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x309b4  ldarg.1
0x309b5  ldstr    aAllowsanonymou// "AllowsAnonymousAccess"
0x309ba  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x309bf  ldarg.1
0x309c0  ldloc.0
0x309c1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_AllowsAnonymousAccess()
0x309c6  ldarg.3
0x309c7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x309cc  ldarg.1
0x309cd  ldstr    aCreated// "Created"
0x309d2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x309d7  ldarg.1
0x309d8  ldloc.0
0x309d9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Created()
0x309de  ldarg.3
0x309df  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x309e4  ldarg.1
0x309e5  ldstr    aCreatedby// "CreatedBy"
0x309ea  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x309ef  ldarg.1
0x309f0  ldloc.0
0x309f1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_CreatedBy()
0x309f6  ldarg.3
0x309f7  call     T0x2B000003
0x309fc  ldarg.1
0x309fd  ldstr    aExpiration// "Expiration"
0x30a02  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a07  ldarg.1
0x30a08  ldloc.0
0x30a09  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Expiration()
0x30a0e  ldarg.3
0x30a0f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30a14  ldarg.1
0x30a15  ldstr    aHasexternalgue// "HasExternalGuestInvitees"
0x30a1a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a1f  ldarg.1
0x30a20  ldloc.0
0x30a21  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_HasExternalGuestInvitees()
0x30a26  ldarg.3
0x30a27  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30a2c  ldarg.1
0x30a2d  ldstr    aInvitations// "Invitations"
0x30a32  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a37  ldarg.1
0x30a38  ldloc.0
0x30a39  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.LinkInvitation> [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Invitations()
0x30a3e  ldarg.3
0x30a3f  call     T0x2B00011A
0x30a44  ldarg.1
0x30a45  ldstr    aIsactive// "IsActive"
0x30a4a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a4f  ldarg.1
0x30a50  ldloc.0
0x30a51  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsActive()
0x30a56  ldarg.3
0x30a57  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30a5c  ldarg.1
0x30a5d  ldstr    aIseditlink// "IsEditLink"
0x30a62  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a67  ldarg.1
0x30a68  ldloc.0
0x30a69  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsEditLink()
0x30a6e  ldarg.3
0x30a6f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30a74  ldarg.1
0x30a75  ldstr    aIsformslink// "IsFormsLink"
0x30a7a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a7f  ldarg.1
0x30a80  ldloc.0
0x30a81  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsFormsLink()
0x30a86  ldarg.3
0x30a87  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30a8c  ldarg.1
0x30a8d  ldstr    aIsreviewlink// "IsReviewLink"
0x30a92  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30a97  ldarg.1
0x30a98  ldloc.0
0x30a99  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsReviewLink()
0x30a9e  ldarg.3
0x30a9f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30aa4  ldarg.1
0x30aa5  ldstr    aIsunhealthy// "IsUnhealthy"
0x30aaa  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30aaf  ldarg.1
0x30ab0  ldloc.0
0x30ab1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_IsUnhealthy()
0x30ab6  ldarg.3
0x30ab7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30abc  ldarg.1
0x30abd  ldstr    aLastmodified// "LastModified"
0x30ac2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30ac7  ldarg.1
0x30ac8  ldloc.0
0x30ac9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LastModified()
0x30ace  ldarg.3
0x30acf  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30ad4  ldarg.1
0x30ad5  ldstr    aLastmodifiedby// "LastModifiedBy"
0x30ada  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30adf  ldarg.1
0x30ae0  ldloc.0
0x30ae1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Principal [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LastModifiedBy()
0x30ae6  ldarg.3
0x30ae7  call     T0x2B000003
0x30aec  ldarg.1
0x30aed  ldstr    aLinkkind// "LinkKind"
0x30af2  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30af7  ldarg.1
0x30af8  ldloc.0
0x30af9  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_LinkKind()
0x30afe  ldarg.3
0x30aff  call     T0x2B000112
0x30b04  ldarg.1
0x30b05  ldstr    aRequirespasswo// "RequiresPassword"
0x30b0a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30b0f  ldarg.1
0x30b10  ldloc.0
0x30b11  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_RequiresPassword()
0x30b16  ldarg.3
0x30b17  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30b1c  ldarg.1
0x30b1d  ldstr    aRestrictedshar// "RestrictedShareMembership"
0x30b22  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30b27  ldarg.1
0x30b28  ldloc.0
0x30b29  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_RestrictedShareMembership()
0x30b2e  ldarg.3
0x30b2f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30b34  ldarg.1
0x30b35  ldstr    aShareid// "ShareId"
0x30b3a  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30b3f  ldarg.1
0x30b40  ldloc.0
0x30b41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_ShareId()
0x30b46  ldarg.3
0x30b47  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30b4c  ldarg.1
0x30b4d  ldstr    aUrl// "Url"
0x30b52  callvirt instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter::WriteName(string)
0x30b57  ldarg.1
0x30b58  ldloc.0
0x30b59  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo::get_Url()
0x30b5e  ldarg.3
0x30b5f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x30b64  ret
```
