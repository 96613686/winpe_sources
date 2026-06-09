# Microsoft.SharePoint.Sharing.SharingInformationServerStub::SetProperty_0

- ea: `0xaf900`
- end: `0xafcb2`
- name: `Microsoft.SharePoint.Sharing.SharingInformationServerStub::SetProperty_0`
- size: `946`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xaf900`

## string_xrefs

- `0xaf959`: `anonymousLinkExpirationRestrictionDays`
- `0xafab9`: `anonymousLinkExpirationRestrictionDays`
- `0xaf989`: `canRequestAccessForGrantAccess`
- `0xafb21`: `canRequestAccessForGrantAccess`
- `0xaf9b9`: `defaultLinkKind`
- `0xafb89`: `defaultLinkKind`
- `0xaf9c5`: `defaultShareLinkPermission`
- `0xafba3`: `defaultShareLinkPermission`
- `0xaf9ec`: `microserviceShareUiUrl`
- `0xafbf1`: `microserviceShareUiUrl`

## pseudocode

```c

```

## disassembly

```asm
0xaf900  ldarg.s  4
0xaf902  brtrue.s loc_AF90F
0xaf904  ldstr    aProxycontext// "proxyContext"
0xaf909  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaf90e  throw
0xaf90f  ldarg.1
0xaf910  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation
0xaf915  stloc.0
0xaf916  ldloc.0
0xaf917  brtrue.s loc_AF924
0xaf919  ldstr    aTarget// "target"
0xaf91e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaf923  throw
0xaf924  ldarg.2
0xaf925  brtrue.s loc_AF932
0xaf927  ldstr    aPropname// "propName"
0xaf92c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaf931  throw
0xaf932  ldarg.0
0xaf933  ldarg.2
0xaf934  ldarg.s  4
0xaf936  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xaf93b  starg.s  2
0xaf93d  ldarg.2
0xaf93e  dup
0xaf93f  stloc.1
0xaf940  brfalse  loc_AFCA6
0xaf945  volatile.
0xaf947  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c84-1
0xaf94c  brtrue   loc_AFA4D
0xaf951  ldc.i4.s 0x13
0xaf953  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xaf958  dup
0xaf959  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xaf95e  ldc.i4.0
0xaf95f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf964  dup
0xaf965  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xaf96a  ldc.i4.1
0xaf96b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf970  dup
0xaf971  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xaf976  ldc.i4.2
0xaf977  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf97c  dup
0xaf97d  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xaf982  ldc.i4.3
0xaf983  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf988  dup
0xaf989  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xaf98e  ldc.i4.4
0xaf98f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf994  dup
0xaf995  ldstr    aCansendemail_0// "canSendEmail"
0xaf99a  ldc.i4.5
0xaf99b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9a0  dup
0xaf9a1  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xaf9a6  ldc.i4.6
0xaf9a7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9ac  dup
0xaf9ad  ldstr    aCurrentrole// "currentRole"
0xaf9b2  ldc.i4.7
0xaf9b3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9b8  dup
0xaf9b9  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xaf9be  ldc.i4.8
0xaf9bf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9c4  dup
0xaf9c5  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xaf9ca  ldc.i4.s 9
0xaf9cc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9d1  dup
0xaf9d2  ldstr    aDirecturl// "directUrl"
0xaf9d7  ldc.i4.s 0xA
0xaf9d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9de  dup
0xaf9df  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xaf9e4  ldc.i4.s 0xB
0xaf9e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9eb  dup
0xaf9ec  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xaf9f1  ldc.i4.s 0xC
0xaf9f3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xaf9f8  dup
0xaf9f9  ldstr    aSharedobjectty// "sharedObjectType"
0xaf9fe  ldc.i4.s 0xD
0xafa00  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa05  dup
0xafa06  ldstr    aShareuiurl// "shareUiUrl"
0xafa0b  ldc.i4.s 0xE
0xafa0d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa12  dup
0xafa13  ldstr    aSharingabiliti// "sharingAbilities"
0xafa18  ldc.i4.s 0xF
0xafa1a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa1f  dup
0xafa20  ldstr    aSharingstatus// "sharingStatus"
0xafa25  ldc.i4.s 0x10
0xafa27  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa2c  dup
0xafa2d  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xafa32  ldc.i4.s 0x11
0xafa34  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa39  dup
0xafa3a  ldstr    aWeburl_0// "webUrl"
0xafa3f  ldc.i4.s 0x12
0xafa41  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xafa46  volatile.
0xafa48  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c84-1
0xafa4d  volatile.
0xafa4f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001c84-1
0xafa54  ldloc.1
0xafa55  ldloca.s 2
0xafa57  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xafa5c  brfalse  loc_AFCA6
0xafa61  ldloc.2
0xafa62  switch   loc_AFAB8, loc_AFAD2, loc_AFAEC, loc_AFB06, loc_AFB20, loc_AFB3A, loc_AFB54, loc_AFB6E, loc_AFB88, loc_AFBA2, loc_AFBBC, loc_AFBD6, loc_AFBF0, loc_AFC0A, loc_AFC24, loc_AFC3E, loc_AFC58, loc_AFC72, loc_AFC8C
0xafab3  br       loc_AFCA6
0xafab8  ldarg.0
0xafab9  ldstr    aAnonymouslinke// "anonymousLinkExpirationRestrictionDays"
0xafabe  ldarg.s  4
0xafac0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafac5  ldloc.0
0xafac6  ldarg.3
0xafac7  callvirt T0x2B000009
0xafacc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_AnonymousLinkExpirationRestrictionDays(int32)
0xafad1  ret
0xafad2  ldarg.0
0xafad3  ldstr    aBlockpeoplepic_0// "blockPeoplePickerAndSharing"
0xafad8  ldarg.s  4
0xafada  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafadf  ldloc.0
0xafae0  ldarg.3
0xafae1  callvirt T0x2B00000A
0xafae6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_BlockPeoplePickerAndSharing(bool)
0xafaeb  ret
0xafaec  ldarg.0
0xafaed  ldstr    aCanaddexternal// "canAddExternalPrincipal"
0xafaf2  ldarg.s  4
0xafaf4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafaf9  ldloc.0
0xafafa  ldarg.3
0xafafb  callvirt T0x2B00000A
0xafb00  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanAddExternalPrincipal(bool)
0xafb05  ret
0xafb06  ldarg.0
0xafb07  ldstr    aCanaddinternal// "canAddInternalPrincipal"
0xafb0c  ldarg.s  4
0xafb0e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb13  ldloc.0
0xafb14  ldarg.3
0xafb15  callvirt T0x2B00000A
0xafb1a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanAddInternalPrincipal(bool)
0xafb1f  ret
0xafb20  ldarg.0
0xafb21  ldstr    aCanrequestacce// "canRequestAccessForGrantAccess"
0xafb26  ldarg.s  4
0xafb28  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb2d  ldloc.0
0xafb2e  ldarg.3
0xafb2f  callvirt T0x2B00000A
0xafb34  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanRequestAccessForGrantAccess(bool)
0xafb39  ret
0xafb3a  ldarg.0
0xafb3b  ldstr    aCansendemail_0// "canSendEmail"
0xafb40  ldarg.s  4
0xafb42  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb47  ldloc.0
0xafb48  ldarg.3
0xafb49  callvirt T0x2B00000A
0xafb4e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanSendEmail(bool)
0xafb53  ret
0xafb54  ldarg.0
0xafb55  ldstr    aCanusesimplifi// "canUseSimplifiedRoles"
0xafb5a  ldarg.s  4
0xafb5c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb61  ldloc.0
0xafb62  ldarg.3
0xafb63  callvirt T0x2B00000A
0xafb68  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CanUseSimplifiedRoles(bool)
0xafb6d  ret
0xafb6e  ldarg.0
0xafb6f  ldstr    aCurrentrole// "currentRole"
0xafb74  ldarg.s  4
0xafb76  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb7b  ldloc.0
0xafb7c  ldarg.3
0xafb7d  callvirt T0x2B000293
0xafb82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_CurrentRole(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role)
0xafb87  ret
0xafb88  ldarg.0
0xafb89  ldstr    aDefaultlinkkin// "defaultLinkKind"
0xafb8e  ldarg.s  4
0xafb90  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafb95  ldloc.0
0xafb96  ldarg.3
0xafb97  callvirt T0x2B000117
0xafb9c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DefaultLinkKind(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind)
0xafba1  ret
0xafba2  ldarg.0
0xafba3  ldstr    aDefaultshareli_1// "defaultShareLinkPermission"
0xafba8  ldarg.s  4
0xafbaa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafbaf  ldloc.0
0xafbb0  ldarg.3
0xafbb1  callvirt T0x2B000293
0xafbb6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DefaultShareLinkPermission(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.Role)
0xafbbb  ret
0xafbbc  ldarg.0
0xafbbd  ldstr    aDirecturl// "directUrl"
0xafbc2  ldarg.s  4
0xafbc4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafbc9  ldloc.0
0xafbca  ldarg.3
0xafbcb  callvirt T0x2B000008
0xafbd0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_DirectUrl(string)
0xafbd5  ret
0xafbd6  ldarg.0
0xafbd7  ldstr    aHasuniquepermi// "hasUniquePermissions"
0xafbdc  ldarg.s  4
0xafbde  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafbe3  ldloc.0
0xafbe4  ldarg.3
0xafbe5  callvirt T0x2B00000A
0xafbea  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_HasUniquePermissions(bool)
0xafbef  ret
0xafbf0  ldarg.0
0xafbf1  ldstr    aMicroservicesh// "microserviceShareUiUrl"
0xafbf6  ldarg.s  4
0xafbf8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafbfd  ldloc.0
0xafbfe  ldarg.3
0xafbff  callvirt T0x2B000008
0xafc04  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_MicroserviceShareUiUrl(string)
0xafc09  ret
0xafc0a  ldarg.0
0xafc0b  ldstr    aSharedobjectty// "sharedObjectType"
0xafc10  ldarg.s  4
0xafc12  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc17  ldloc.0
0xafc18  ldarg.3
0xafc19  callvirt T0x2B000118
0xafc1e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharedObjectType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SPSharedObjectType)
0xafc23  ret
0xafc24  ldarg.0
0xafc25  ldstr    aShareuiurl// "shareUiUrl"
0xafc2a  ldarg.s  4
0xafc2c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc31  ldloc.0
0xafc32  ldarg.3
0xafc33  callvirt T0x2B000008
0xafc38  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_ShareUiUrl(string)
0xafc3d  ret
0xafc3e  ldarg.0
0xafc3f  ldstr    aSharingabiliti// "sharingAbilities"
0xafc44  ldarg.s  4
0xafc46  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc4b  ldloc.0
0xafc4c  ldarg.3
0xafc4d  callvirt T0x2B0002A5
0xafc52  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharingAbilities(class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingAbilities)
0xafc57  ret
0xafc58  ldarg.0
0xafc59  ldstr    aSharingstatus// "sharingStatus"
0xafc5e  ldarg.s  4
0xafc60  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc65  ldloc.0
0xafc66  ldarg.3
0xafc67  callvirt T0x2B0002A6
0xafc6c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_SharingStatus(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingStatus)
0xafc71  ret
0xafc72  ldarg.0
0xafc73  ldstr    aShowexternalsh_0// "showExternalSharingWarning"
0xafc78  ldarg.s  4
0xafc7a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc7f  ldloc.0
0xafc80  ldarg.3
0xafc81  callvirt T0x2B00000A
0xafc86  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_ShowExternalSharingWarning(bool)
0xafc8b  ret
0xafc8c  ldarg.0
0xafc8d  ldstr    aWeburl_0// "webUrl"
0xafc92  ldarg.s  4
0xafc94  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafc99  ldloc.0
0xafc9a  ldarg.3
0xafc9b  callvirt T0x2B000008
0xafca0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharingInformation::set_WebUrl(string)
0xafca5  ret
0xafca6  ldarg.0
0xafca7  ldarg.1
0xafca8  ldarg.2
0xafca9  ldarg.3
0xafcaa  ldarg.s  4
0xafcac  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xafcb1  ret
```
