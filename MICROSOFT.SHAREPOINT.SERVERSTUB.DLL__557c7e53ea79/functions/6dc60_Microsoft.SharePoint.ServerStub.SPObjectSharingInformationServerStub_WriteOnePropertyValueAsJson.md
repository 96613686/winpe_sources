# Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::WriteOnePropertyValueAsJson

- ea: `0x6dc60`
- end: `0x6e273`
- name: `Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::WriteOnePropertyValueAsJson`
- size: `1555`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6dc60`

## string_xrefs

- `0x6dc98`: `AnonymousEditLink`
- `0x6dded`: `AnonymousEditLink`
- `0x6dca4`: `AnonymousViewLink`
- `0x6de37`: `AnonymousViewLink`
- `0x6dcd4`: `HasPendingAccessRequests`
- `0x6df5f`: `HasPendingAccessRequests`
- `0x6dd1e`: `IsSharedWithSecurityGroup`
- `0x6e11b`: `IsSharedWithSecurityGroup`
- `0x6dd2b`: `PendingAccessRequestsLink`
- `0x6e165`: `PendingAccessRequestsLink`
- `0x6dd45`: `SharingLinks`
- `0x6e200`: `SharingLinks`

## pseudocode

```c

```

## disassembly

```asm
0x6dc60  ldc.i4.0
0x6dc61  stloc.0
0x6dc62  ldarg.2
0x6dc63  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation
0x6dc68  stloc.1
0x6dc69  ldloc.1
0x6dc6a  brtrue.s loc_6DC77
0x6dc6c  ldstr    aTarget// "target"
0x6dc71  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6dc76  throw
0x6dc77  ldarg.3
0x6dc78  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x6dc7d  dup
0x6dc7e  stloc.2
0x6dc7f  brfalse  loc_6E265
0x6dc84  volatile.
0x6dc86  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001343-1
0x6dc8b  brtrue   loc_6DD65
0x6dc90  ldc.i4.s 0x10
0x6dc92  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6dc97  dup
0x6dc98  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6dc9d  ldc.i4.0
0x6dc9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dca3  dup
0x6dca4  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6dca9  ldc.i4.1
0x6dcaa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcaf  dup
0x6dcb0  ldstr    aCanbeshared// "CanBeShared"
0x6dcb5  ldc.i4.2
0x6dcb6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcbb  dup
0x6dcbc  ldstr    aCanbeunshared// "CanBeUnshared"
0x6dcc1  ldc.i4.3
0x6dcc2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcc7  dup
0x6dcc8  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6dccd  ldc.i4.4
0x6dcce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcd3  dup
0x6dcd4  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6dcd9  ldc.i4.5
0x6dcda  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcdf  dup
0x6dce0  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6dce5  ldc.i4.6
0x6dce6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dceb  dup
0x6dcec  ldstr    aIsfolder// "IsFolder"
0x6dcf1  ldc.i4.7
0x6dcf2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dcf7  dup
0x6dcf8  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6dcfd  ldc.i4.8
0x6dcfe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd03  dup
0x6dd04  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6dd09  ldc.i4.s 9
0x6dd0b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd10  dup
0x6dd11  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6dd16  ldc.i4.s 0xA
0x6dd18  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd1d  dup
0x6dd1e  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6dd23  ldc.i4.s 0xB
0x6dd25  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd2a  dup
0x6dd2b  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6dd30  ldc.i4.s 0xC
0x6dd32  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd37  dup
0x6dd38  ldstr    aSharedwithuser_0// "SharedWithUsersCollection"
0x6dd3d  ldc.i4.s 0xD
0x6dd3f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd44  dup
0x6dd45  ldstr    aSharinglinks// "SharingLinks"
0x6dd4a  ldc.i4.s 0xE
0x6dd4c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd51  dup
0x6dd52  ldstr    aTotalfilecount// "TotalFileCount"
0x6dd57  ldc.i4.s 0xF
0x6dd59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6dd5e  volatile.
0x6dd60  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001343-1
0x6dd65  volatile.
0x6dd67  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001343-1
0x6dd6c  ldloc.2
0x6dd6d  ldloca.s 3
0x6dd6f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6dd74  brfalse  loc_6E265
0x6dd79  ldloc.3
0x6dd7a  switch   loc_6DDC4, loc_6DE0E, loc_6DE58, loc_6DEA2, loc_6DEEC, loc_6DF36, loc_6DF80, loc_6DFCA, loc_6E014, loc_6E05E, loc_6E0A8, loc_6E0F2, loc_6E13C, loc_6E186, loc_6E1D7, loc_6E21E
0x6ddbf  br       loc_6E265
0x6ddc4  ldarg.3
0x6ddc5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6ddca  stloc.s  4
0x6ddcc  ldloca.s 4
0x6ddce  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6ddd3  brfalse.s loc_6DDEC
0x6ddd5  ldarg.3
0x6ddd6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6dddb  stloc.s  5
0x6dddd  ldloca.s 5
0x6dddf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6dde4  brtrue.s loc_6DDEC
0x6dde6  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6ddeb  throw
0x6ddec  ldarg.0
0x6dded  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6ddf2  ldarg.s  4
0x6ddf4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ddf9  ldc.i4.1
0x6ddfa  stloc.0
0x6ddfb  ldarg.1
0x6ddfc  ldloc.1
0x6ddfd  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousEditLink()
0x6de02  ldarg.s  4
0x6de04  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6de09  br       loc_6E271
0x6de0e  ldarg.3
0x6de0f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6de14  stloc.s  6
0x6de16  ldloca.s 6
0x6de18  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6de1d  brfalse.s loc_6DE36
0x6de1f  ldarg.3
0x6de20  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6de25  stloc.s  7
0x6de27  ldloca.s 7
0x6de29  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6de2e  brtrue.s loc_6DE36
0x6de30  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6de35  throw
0x6de36  ldarg.0
0x6de37  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6de3c  ldarg.s  4
0x6de3e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6de43  ldc.i4.1
0x6de44  stloc.0
0x6de45  ldarg.1
0x6de46  ldloc.1
0x6de47  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousViewLink()
0x6de4c  ldarg.s  4
0x6de4e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6de53  br       loc_6E271
0x6de58  ldarg.3
0x6de59  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6de5e  stloc.s  8
0x6de60  ldloca.s 8
0x6de62  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6de67  brfalse.s loc_6DE80
0x6de69  ldarg.3
0x6de6a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6de6f  stloc.s  9
0x6de71  ldloca.s 9
0x6de73  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6de78  brtrue.s loc_6DE80
0x6de7a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6de7f  throw
0x6de80  ldarg.0
0x6de81  ldstr    aCanbeshared// "CanBeShared"
0x6de86  ldarg.s  4
0x6de88  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6de8d  ldc.i4.1
0x6de8e  stloc.0
0x6de8f  ldarg.1
0x6de90  ldloc.1
0x6de91  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeShared()
0x6de96  ldarg.s  4
0x6de98  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6de9d  br       loc_6E271
0x6dea2  ldarg.3
0x6dea3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6dea8  stloc.s  0xA
0x6deaa  ldloca.s 0xA
0x6deac  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6deb1  brfalse.s loc_6DECA
0x6deb3  ldarg.3
0x6deb4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6deb9  stloc.s  0xB
0x6debb  ldloca.s 0xB
0x6debd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6dec2  brtrue.s loc_6DECA
0x6dec4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6dec9  throw
0x6deca  ldarg.0
0x6decb  ldstr    aCanbeunshared// "CanBeUnshared"
0x6ded0  ldarg.s  4
0x6ded2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ded7  ldc.i4.1
0x6ded8  stloc.0
0x6ded9  ldarg.1
0x6deda  ldloc.1
0x6dedb  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeUnshared()
0x6dee0  ldarg.s  4
0x6dee2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6dee7  br       loc_6E271
0x6deec  ldarg.3
0x6deed  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6def2  stloc.s  0xC
0x6def4  ldloca.s 0xC
0x6def6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6defb  brfalse.s loc_6DF14
0x6defd  ldarg.3
0x6defe  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6df03  stloc.s  0xD
0x6df05  ldloca.s 0xD
0x6df07  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6df0c  brtrue.s loc_6DF14
0x6df0e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6df13  throw
0x6df14  ldarg.0
0x6df15  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6df1a  ldarg.s  4
0x6df1c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6df21  ldc.i4.1
0x6df22  stloc.0
0x6df23  ldarg.1
0x6df24  ldloc.1
0x6df25  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanManagePermissions()
0x6df2a  ldarg.s  4
0x6df2c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6df31  br       loc_6E271
0x6df36  ldarg.3
0x6df37  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6df3c  stloc.s  0xE
0x6df3e  ldloca.s 0xE
0x6df40  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6df45  brfalse.s loc_6DF5E
0x6df47  ldarg.3
0x6df48  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6df4d  stloc.s  0xF
0x6df4f  ldloca.s 0xF
0x6df51  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6df56  brtrue.s loc_6DF5E
0x6df58  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6df5d  throw
0x6df5e  ldarg.0
0x6df5f  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6df64  ldarg.s  4
0x6df66  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6df6b  ldc.i4.1
0x6df6c  stloc.0
0x6df6d  ldarg.1
0x6df6e  ldloc.1
0x6df6f  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPendingAccessRequests()
0x6df74  ldarg.s  4
0x6df76  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6df7b  br       loc_6E271
0x6df80  ldarg.3
0x6df81  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6df86  stloc.s  0x10
0x6df88  ldloca.s 0x10
0x6df8a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6df8f  brfalse.s loc_6DFA8
0x6df91  ldarg.3
0x6df92  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6df97  stloc.s  0x11
0x6df99  ldloca.s 0x11
0x6df9b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6dfa0  brtrue.s loc_6DFA8
0x6dfa2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6dfa7  throw
0x6dfa8  ldarg.0
0x6dfa9  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6dfae  ldarg.s  4
0x6dfb0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6dfb5  ldc.i4.1
0x6dfb6  stloc.0
0x6dfb7  ldarg.1
0x6dfb8  ldloc.1
0x6dfb9  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPermissionLevels()
0x6dfbe  ldarg.s  4
0x6dfc0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6dfc5  br       loc_6E271
0x6dfca  ldarg.3
0x6dfcb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6dfd0  stloc.s  0x12
0x6dfd2  ldloca.s 0x12
0x6dfd4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x6dfd9  brfalse.s loc_6DFF2
0x6dfdb  ldarg.3
0x6dfdc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x6dfe1  stloc.s  0x13
0x6dfe3  ldloca.s 0x13
0x6dfe5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x6dfea  brtrue.s loc_6DFF2
0x6dfec  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x6dff1  throw
0x6dff2  ldarg.0
0x6dff3  ldstr    aIsfolder// "IsFolder"
0x6dff8  ldarg.s  4
0x6dffa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6dfff  ldc.i4.1
0x6e000  stloc.0
0x6e001  ldarg.1
0x6e002  ldloc.1
0x6e003  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsFolder()
  ... truncated ...
```
