# Microsoft.SharePoint.Sharing.SharingInformationServerStub::WriteOnePropertyValueAsJson

- ea: `0xaeba0`
- end: `0xaf430`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::WriteOnePropertyValueAsJson`
- size: `2192`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xaeba0`

## string_xrefs

- `0xaebd8`: `accessRequestSettings`
- `0xaeda4`: `accessRequestSettings`
- `0xaebe4`: `anonymousLinkExpirationRestrictionDays`
- `0xaedee`: `anonymousLinkExpirationRestrictionDays`
- `0xaec14`: `canRequestAccessForGrantAccess`
- `0xaef16`: `canRequestAccessForGrantAccess`
- `0xaec44`: `defaultLinkKind`
- `0xaf03e`: `defaultLinkKind`
- `0xaec51`: `defaultShareLinkPermission`
- `0xaf088`: `defaultShareLinkPermission`
- `0xaec85`: `microserviceShareUiUrl`
- `0xaf1b0`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xaeba0  ldc.i4.0
0xaeba1  stloc.0
0xaeba2  ldarg.2
0xaeba3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation
0xaeba8  stloc.1
0xaeba9  ldloc.1
0xaebaa  brtrue.s loc_AEBB7
0xaebac  ldstr    aTarget// "target"
0xaebb1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaebb6  throw
0xaebb7  ldarg.3
0xaebb8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0xaebbd  dup
0xaebbe  stloc.2
0xaebbf  brfalse  loc_AF422
0xaebc4  volatile.
0xaebc6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7f-1
0xaebcb  brtrue   loc_AED00
0xaebd0  ldc.i4.s 0x17
0xaebd2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xaebd7  dup
0xaebd8  ldstr    aAccessrequests// "accessRequestSettings"
0xaebdd  ldc.i4.0
0xaebde  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaebe3  dup
0xaebe4  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaebe9  ldc.i4.1
0xaebea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaebef  dup
0xaebf0  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaebf5  ldc.i4.2
0xaebf6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaebfb  dup
0xaebfc  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaec01  ldc.i4.3
0xaec02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec07  dup
0xaec08  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaec0d  ldc.i4.4
0xaec0e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec13  dup
0xaec14  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaec19  ldc.i4.5
0xaec1a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec1f  dup
0xaec20  ldstr    aCansendemail_0// "canSendEmail"
0xaec25  ldc.i4.6
0xaec26  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec2b  dup
0xaec2c  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaec31  ldc.i4.7
0xaec32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec37  dup
0xaec38  ldstr    aCurrentrole// "currentRole"
0xaec3d  ldc.i4.8
0xaec3e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec43  dup
0xaec44  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaec49  ldc.i4.s 9
0xaec4b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec50  dup
0xaec51  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaec56  ldc.i4.s 0xA
0xaec58  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec5d  dup
0xaec5e  ldstr    aDirecturl// "directUrl"
0xaec63  ldc.i4.s 0xB
0xaec65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec6a  dup
0xaec6b  ldstr    aDomainrestrict_3// "domainRestrictionSettings"
0xaec70  ldc.i4.s 0xC
0xaec72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec77  dup
0xaec78  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaec7d  ldc.i4.s 0xD
0xaec7f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec84  dup
0xaec85  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaec8a  ldc.i4.s 0xE
0xaec8c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec91  dup
0xaec92  ldstr    aPermissionsinf// "permissionsInformation"
0xaec97  ldc.i4.s 0xF
0xaec99  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaec9e  dup
0xaec9f  ldstr    aPickersettings// "pickerSettings"
0xaeca4  ldc.i4.s 0x10
0xaeca6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecab  dup
0xaecac  ldstr    aSharedobjectty// "sharedObjectType"
0xaecb1  ldc.i4.s 0x11
0xaecb3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecb8  dup
0xaecb9  ldstr    aShareuiurl// "shareUiUrl"
0xaecbe  ldc.i4.s 0x12
0xaecc0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecc5  dup
0xaecc6  ldstr    aSharingabiliti// "sharingAbilities"
0xaeccb  ldc.i4.s 0x13
0xaeccd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecd2  dup
0xaecd3  ldstr    aSharingstatus// "sharingStatus"
0xaecd8  ldc.i4.s 0x14
0xaecda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecdf  dup
0xaece0  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xaece5  ldc.i4.s 0x15
0xaece7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecec  dup
0xaeced  ldstr    aWeburl_0// "webUrl"
0xaecf2  ldc.i4.s 0x16
0xaecf4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaecf9  volatile.
0xaecfb  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7f-1
0xaed00  volatile.
0xaed02  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c7f-1
0xaed07  ldloc.2
0xaed08  ldloca.s 3
0xaed0a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xaed0f  brfalse  loc_AF422
0xaed14  ldloc.3
0xaed15  switch   loc_AED7B, loc_AEDC5, loc_AEE0F, loc_AEE59, loc_AEEA3, loc_AEEED, loc_AEF37, loc_AEF81, loc_AEFCB, loc_AF015, loc_AF05F, loc_AF0A9, loc_AF0F3, loc_AF13D, loc_AF187, loc_AF1D1, loc_AF21B, loc_AF26C, loc_AF2B6, loc_AF300, loc_AF34A, loc_AF394, loc_AF3DB
0xaed76  br       loc_AF422
0xaed7b  ldarg.3
0xaed7c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaed81  stloc.s  4
0xaed83  ldloca.s 4
0xaed85  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaed8a  brfalse.s loc_AEDA3
0xaed8c  ldarg.3
0xaed8d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaed92  stloc.s  5
0xaed94  ldloca.s 5
0xaed96  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaed9b  brtrue.s loc_AEDA3
0xaed9d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaeda2  throw
0xaeda3  ldarg.0
0xaeda4  ldstr    aAccessrequests// "accessRequestSettings"
0xaeda9  ldarg.s  4
0xaedab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaedb0  ldc.i4.1
0xaedb1  stloc.0
0xaedb2  ldarg.1
0xaedb3  ldloc.1
0xaedb4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.AccessRequestSettings [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_AccessRequestSettings()
0xaedb9  ldarg.s  4
0xaedbb  call     T0x2B0002A0
0xaedc0  br       loc_AF42E
0xaedc5  ldarg.3
0xaedc6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaedcb  stloc.s  6
0xaedcd  ldloca.s 6
0xaedcf  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaedd4  brfalse.s loc_AEDED
0xaedd6  ldarg.3
0xaedd7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaeddc  stloc.s  7
0xaedde  ldloca.s 7
0xaede0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaede5  brtrue.s loc_AEDED
0xaede7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaedec  throw
0xaeded  ldarg.0
0xaedee  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaedf3  ldarg.s  4
0xaedf5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaedfa  ldc.i4.1
0xaedfb  stloc.0
0xaedfc  ldarg.1
0xaedfd  ldloc.1
0xaedfe  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_AnonymousLinkExpirationRestrictionDays()
0xaee03  ldarg.s  4
0xaee05  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaee0a  br       loc_AF42E
0xaee0f  ldarg.3
0xaee10  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaee15  stloc.s  8
0xaee17  ldloca.s 8
0xaee19  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaee1e  brfalse.s loc_AEE37
0xaee20  ldarg.3
0xaee21  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaee26  stloc.s  9
0xaee28  ldloca.s 9
0xaee2a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaee2f  brtrue.s loc_AEE37
0xaee31  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaee36  throw
0xaee37  ldarg.0
0xaee38  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaee3d  ldarg.s  4
0xaee3f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaee44  ldc.i4.1
0xaee45  stloc.0
0xaee46  ldarg.1
0xaee47  ldloc.1
0xaee48  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_BlockPeoplePickerAndSharing()
0xaee4d  ldarg.s  4
0xaee4f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaee54  br       loc_AF42E
0xaee59  ldarg.3
0xaee5a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaee5f  stloc.s  0xA
0xaee61  ldloca.s 0xA
0xaee63  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaee68  brfalse.s loc_AEE81
0xaee6a  ldarg.3
0xaee6b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaee70  stloc.s  0xB
0xaee72  ldloca.s 0xB
0xaee74  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaee79  brtrue.s loc_AEE81
0xaee7b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaee80  throw
0xaee81  ldarg.0
0xaee82  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaee87  ldarg.s  4
0xaee89  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaee8e  ldc.i4.1
0xaee8f  stloc.0
0xaee90  ldarg.1
0xaee91  ldloc.1
0xaee92  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddExternalPrincipal()
0xaee97  ldarg.s  4
0xaee99  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaee9e  br       loc_AF42E
0xaeea3  ldarg.3
0xaeea4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaeea9  stloc.s  0xC
0xaeeab  ldloca.s 0xC
0xaeead  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaeeb2  brfalse.s loc_AEECB
0xaeeb4  ldarg.3
0xaeeb5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaeeba  stloc.s  0xD
0xaeebc  ldloca.s 0xD
0xaeebe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaeec3  brtrue.s loc_AEECB
0xaeec5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaeeca  throw
0xaeecb  ldarg.0
0xaeecc  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaeed1  ldarg.s  4
0xaeed3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeed8  ldc.i4.1
0xaeed9  stloc.0
0xaeeda  ldarg.1
0xaeedb  ldloc.1
0xaeedc  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanAddInternalPrincipal()
0xaeee1  ldarg.s  4
0xaeee3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaeee8  br       loc_AF42E
0xaeeed  ldarg.3
0xaeeee  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaeef3  stloc.s  0xE
0xaeef5  ldloca.s 0xE
0xaeef7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaeefc  brfalse.s loc_AEF15
0xaeefe  ldarg.3
0xaeeff  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaef04  stloc.s  0xF
0xaef06  ldloca.s 0xF
0xaef08  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaef0d  brtrue.s loc_AEF15
0xaef0f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaef14  throw
0xaef15  ldarg.0
0xaef16  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaef1b  ldarg.s  4
0xaef1d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaef22  ldc.i4.1
0xaef23  stloc.0
0xaef24  ldarg.1
0xaef25  ldloc.1
0xaef26  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::get_CanRequestAccessForGrantAccess()
0xaef2b  ldarg.s  4
0xaef2d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaef32  br       loc_AF42E
0xaef37  ldarg.3
0xaef38  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaef3d  stloc.s  0x10
0xaef3f  ldloca.s 0x10
0xaef41  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xaef46  brfalse.s loc_AEF5F
0xaef48  ldarg.3
0xaef49  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0xaef4e  stloc.s  0x11
0xaef50  ldloca.s 0x11
0xaef52  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xaef57  brtrue.s loc_AEF5F
0xaef59  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0xaef5e  throw
0xaef5f  ldarg.0
0xaef60  ldstr    aCansendemail_0// "canSendEmail"
0xaef65  ldarg.s  4
0xaef67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaef6c  ldc.i4.1
0xaef6d  stloc.0
0xaef6e  ldarg.1
  ... truncated ...
```
