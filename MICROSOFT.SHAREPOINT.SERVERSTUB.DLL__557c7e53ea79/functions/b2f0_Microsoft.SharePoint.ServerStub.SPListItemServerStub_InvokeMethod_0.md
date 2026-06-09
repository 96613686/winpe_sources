# Microsoft.SharePoint.ServerStub.SPListItemServerStub::InvokeMethod_0

- ea: `0xb2f0`
- end: `0xb665`
- name: `Microsoft.SharePoint.ServerStub.SPListItemServerStub::InvokeMethod_0`
- size: `885`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13d0`
- `0xb0e0`
- `0xb0f0`
- `0xb100`
- `0xb110`
- `0xb120`
- `0xb130`
- `0xb140`
- `0xb160`
- `0xb180`
- `0xb1b0`
- `0xb1d0`
- `0xb1e0`
- `0xb210`
- `0xb230`
- `0xb260`
- `0xb290`
- `0xb2d0`
- `0xb2f0`

## string_xrefs

- `0xb33b`: `Update`
- `0xb47d`: `Update`
- `0xb36b`: `DeleteObject`
- `0xb4ed`: `DeleteObject`
- `0xb35f`: `UpdateWithFieldValues`
- `0xb4d1`: `UpdateWithFieldValues`
- `0xb347`: `SystemUpdate`
- `0xb499`: `SystemUpdate`
- `0xb353`: `UpdateOverwriteVersion`
- `0xb4b5`: `UpdateOverwriteVersion`
- `0xb38f`: `SetCommentsDisabled`
- `0xb544`: `SetCommentsDisabled`
- `0xb3f5`: `ValidateUpdateListItem`
- `0xb626`: `ValidateUpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0xb2f0  ldarg.s  4
0xb2f2  brtrue.s loc_B2FF
0xb2f4  ldstr    aProxycontext// "proxyContext"
0xb2f9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb2fe  throw
0xb2ff  ldarg.1
0xb300  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0xb305  stloc.0
0xb306  ldloc.0
0xb307  brtrue.s loc_B314
0xb309  ldstr    aTarget// "target"
0xb30e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb313  throw
0xb314  ldarg.0
0xb315  ldarg.2
0xb316  ldarg.s  4
0xb318  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb31d  starg.s  2
0xb31f  ldarg.2
0xb320  dup
0xb321  stloc.1
0xb322  brfalse  loc_B657
0xb327  volatile.
0xb329  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000156-1
0xb32e  brtrue   loc_B415
0xb333  ldc.i4.s 0x11
0xb335  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb33a  dup
0xb33b  ldstr    aUpdate// "Update"
0xb340  ldc.i4.0
0xb341  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb346  dup
0xb347  ldstr    aSystemupdate// "SystemUpdate"
0xb34c  ldc.i4.1
0xb34d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb352  dup
0xb353  ldstr    aUpdateoverwrit// "UpdateOverwriteVersion"
0xb358  ldc.i4.2
0xb359  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb35e  dup
0xb35f  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0xb364  ldc.i4.3
0xb365  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb36a  dup
0xb36b  ldstr    aDeleteobject// "DeleteObject"
0xb370  ldc.i4.4
0xb371  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb376  dup
0xb377  ldstr    aRecycle// "Recycle"
0xb37c  ldc.i4.5
0xb37d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb382  dup
0xb383  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0xb388  ldc.i4.6
0xb389  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb38e  dup
0xb38f  ldstr    aSetcommentsdis// "SetCommentsDisabled"
0xb394  ldc.i4.7
0xb395  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb39a  dup
0xb39b  ldstr    aOverridepolicy// "OverridePolicyTip"
0xb3a0  ldc.i4.8
0xb3a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3a6  dup
0xb3a7  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0xb3ac  ldc.i4.s 9
0xb3ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3b3  dup
0xb3b4  ldstr    aResetroleinher// "ResetRoleInheritance"
0xb3b9  ldc.i4.s 0xA
0xb3bb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3c0  dup
0xb3c1  ldstr    aBreakroleinher// "BreakRoleInheritance"
0xb3c6  ldc.i4.s 0xB
0xb3c8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3cd  dup
0xb3ce  ldstr    aGetchanges// "GetChanges"
0xb3d3  ldc.i4.s 0xC
0xb3d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3da  dup
0xb3db  ldstr    aSetfieldvalue// "SetFieldValue"
0xb3e0  ldc.i4.s 0xD
0xb3e2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3e7  dup
0xb3e8  ldstr    aParseandsetfie// "ParseAndSetFieldValue"
0xb3ed  ldc.i4.s 0xE
0xb3ef  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb3f4  dup
0xb3f5  ldstr    aValidateupdate// "ValidateUpdateListItem"
0xb3fa  ldc.i4.s 0xF
0xb3fc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb401  dup
0xb402  ldstr    aGetfieldvalue// "GetFieldValue"
0xb407  ldc.i4.s 0x10
0xb409  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb40e  volatile.
0xb410  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000156-1
0xb415  volatile.
0xb417  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000156-1
0xb41c  ldloc.1
0xb41d  ldloca.s 2
0xb41f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb424  brfalse  loc_B657
0xb429  ldloc.2
0xb42a  switch   loc_B478, loc_B494, loc_B4B0, loc_B4CC, loc_B4E8, loc_B504, loc_B524, loc_B53F, loc_B55B, loc_B57B, loc_B596, loc_B5B2, loc_B5CE, loc_B5E9, loc_B605, loc_B621, loc_B63C
0xb473  br       loc_B657
0xb478  ldarg.s  5
0xb47a  ldc.i4.1
0xb47b  stind.i1
0xb47c  ldarg.0
0xb47d  ldstr    aUpdate// "Update"
0xb482  ldarg.s  4
0xb484  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb489  ldloc.0
0xb48a  ldarg.3
0xb48b  ldarg.s  4
0xb48d  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb492  ldnull
0xb493  ret
0xb494  ldarg.s  5
0xb496  ldc.i4.1
0xb497  stind.i1
0xb498  ldarg.0
0xb499  ldstr    aSystemupdate// "SystemUpdate"
0xb49e  ldarg.s  4
0xb4a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb4a5  ldloc.0
0xb4a6  ldarg.3
0xb4a7  ldarg.s  4
0xb4a9  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SystemUpdate_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb4ae  ldnull
0xb4af  ret
0xb4b0  ldarg.s  5
0xb4b2  ldc.i4.1
0xb4b3  stind.i1
0xb4b4  ldarg.0
0xb4b5  ldstr    aUpdateoverwrit// "UpdateOverwriteVersion"
0xb4ba  ldarg.s  4
0xb4bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb4c1  ldloc.0
0xb4c2  ldarg.3
0xb4c3  ldarg.s  4
0xb4c5  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::UpdateOverwriteVersion_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb4ca  ldnull
0xb4cb  ret
0xb4cc  ldarg.s  5
0xb4ce  ldc.i4.1
0xb4cf  stind.i1
0xb4d0  ldarg.0
0xb4d1  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0xb4d6  ldarg.s  4
0xb4d8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb4dd  ldloc.0
0xb4de  ldarg.3
0xb4df  ldarg.s  4
0xb4e1  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::UpdateWithFieldValues_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb4e6  ldnull
0xb4e7  ret
0xb4e8  ldarg.s  5
0xb4ea  ldc.i4.1
0xb4eb  stind.i1
0xb4ec  ldarg.0
0xb4ed  ldstr    aDeleteobject// "DeleteObject"
0xb4f2  ldarg.s  4
0xb4f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb4f9  ldloc.0
0xb4fa  ldarg.3
0xb4fb  ldarg.s  4
0xb4fd  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb502  ldnull
0xb503  ret
0xb504  ldarg.s  5
0xb506  ldc.i4.0
0xb507  stind.i1
0xb508  ldarg.0
0xb509  ldstr    aRecycle// "Recycle"
0xb50e  ldarg.s  4
0xb510  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb515  ldloc.0
0xb516  ldarg.3
0xb517  ldarg.s  4
0xb519  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPListItemServerStub::Recycle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb51e  box      [mscorlib]System.Guid
0xb523  ret
0xb524  ldarg.s  5
0xb526  ldc.i4.0
0xb527  stind.i1
0xb528  ldarg.0
0xb529  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0xb52e  ldarg.s  4
0xb530  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb535  ldloc.0
0xb536  ldarg.3
0xb537  ldarg.s  4
0xb539  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetUserEffectivePermissions_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb53e  ret
0xb53f  ldarg.s  5
0xb541  ldc.i4.1
0xb542  stind.i1
0xb543  ldarg.0
0xb544  ldstr    aSetcommentsdis// "SetCommentsDisabled"
0xb549  ldarg.s  4
0xb54b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb550  ldloc.0
0xb551  ldarg.3
0xb552  ldarg.s  4
0xb554  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SetCommentsDisabled_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb559  ldnull
0xb55a  ret
0xb55b  ldarg.s  5
0xb55d  ldc.i4.0
0xb55e  stind.i1
0xb55f  ldarg.0
0xb560  ldstr    aOverridepolicy// "OverridePolicyTip"
0xb565  ldarg.s  4
0xb567  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb56c  ldloc.0
0xb56d  ldarg.3
0xb56e  ldarg.s  4
0xb570  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPPolicyTipUserActionResult Microsoft.SharePoint.ServerStub.SPListItemServerStub::OverridePolicyTip_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb575  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPPolicyTipUserActionResult
0xb57a  ret
0xb57b  ldarg.s  5
0xb57d  ldc.i4.0
0xb57e  stind.i1
0xb57f  ldarg.0
0xb580  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0xb585  ldarg.s  4
0xb587  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb58c  ldloc.0
0xb58d  ldarg.3
0xb58e  ldarg.s  4
0xb590  call     string Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetWOPIFrameUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb595  ret
0xb596  ldarg.s  5
0xb598  ldc.i4.1
0xb599  stind.i1
0xb59a  ldarg.0
0xb59b  ldstr    aResetroleinher// "ResetRoleInheritance"
0xb5a0  ldarg.s  4
0xb5a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5a7  ldloc.0
0xb5a8  ldarg.3
0xb5a9  ldarg.s  4
0xb5ab  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::ResetRoleInheritance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5b0  ldnull
0xb5b1  ret
0xb5b2  ldarg.s  5
0xb5b4  ldc.i4.1
0xb5b5  stind.i1
0xb5b6  ldarg.0
0xb5b7  ldstr    aBreakroleinher// "BreakRoleInheritance"
0xb5bc  ldarg.s  4
0xb5be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5c3  ldloc.0
0xb5c4  ldarg.3
0xb5c5  ldarg.s  4
0xb5c7  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::BreakRoleInheritance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5cc  ldnull
0xb5cd  ret
0xb5ce  ldarg.s  5
0xb5d0  ldc.i4.0
0xb5d1  stind.i1
0xb5d2  ldarg.0
0xb5d3  ldstr    aGetchanges// "GetChanges"
0xb5d8  ldarg.s  4
0xb5da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5df  ldloc.0
0xb5e0  ldarg.3
0xb5e1  ldarg.s  4
0xb5e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb5e8  ret
0xb5e9  ldarg.s  5
0xb5eb  ldc.i4.1
0xb5ec  stind.i1
0xb5ed  ldarg.0
0xb5ee  ldstr    aSetfieldvalue// "SetFieldValue"
0xb5f3  ldarg.s  4
0xb5f5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb5fa  ldloc.0
0xb5fb  ldarg.3
0xb5fc  ldarg.s  4
0xb5fe  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb603  ldnull
0xb604  ret
0xb605  ldarg.s  5
0xb607  ldc.i4.1
0xb608  stind.i1
0xb609  ldarg.0
0xb60a  ldstr    aParseandsetfie// "ParseAndSetFieldValue"
0xb60f  ldarg.s  4
0xb611  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb616  ldloc.0
0xb617  ldarg.3
0xb618  ldarg.s  4
0xb61a  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::ParseAndSetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb61f  ldnull
0xb620  ret
0xb621  ldarg.s  5
0xb623  ldc.i4.0
  ... truncated ...
```
