# Microsoft.SharePoint.ServerStub.SPListItemServerStub::InvokeMethod

- ea: `0x9cf0`
- end: `0xa065`
- name: `Microsoft.SharePoint.ServerStub.SPListItemServerStub::InvokeMethod`
- size: `885`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1030`
- `0x9ae0`
- `0x9af0`
- `0x9b00`
- `0x9b10`
- `0x9b20`
- `0x9b30`
- `0x9b40`
- `0x9b60`
- `0x9b80`
- `0x9bb0`
- `0x9bd0`
- `0x9be0`
- `0x9c10`
- `0x9c30`
- `0x9c60`
- `0x9c90`
- `0x9cd0`
- `0x9cf0`

## string_xrefs

- `0x9d3b`: `Update`
- `0x9e7d`: `Update`
- `0x9d6b`: `DeleteObject`
- `0x9eed`: `DeleteObject`
- `0x9d5f`: `UpdateWithFieldValues`
- `0x9ed1`: `UpdateWithFieldValues`
- `0x9d47`: `SystemUpdate`
- `0x9e99`: `SystemUpdate`
- `0x9d53`: `UpdateOverwriteVersion`
- `0x9eb5`: `UpdateOverwriteVersion`
- `0x9d8f`: `SetCommentsDisabled`
- `0x9f44`: `SetCommentsDisabled`
- `0x9df5`: `ValidateUpdateListItem`
- `0xa026`: `ValidateUpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0x9cf0  ldarg.s  4
0x9cf2  brtrue.s loc_9CFF
0x9cf4  ldstr    aProxycontext// "proxyContext"
0x9cf9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9cfe  throw
0x9cff  ldarg.1
0x9d00  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem
0x9d05  stloc.0
0x9d06  ldloc.0
0x9d07  brtrue.s loc_9D14
0x9d09  ldstr    aTarget// "target"
0x9d0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9d13  throw
0x9d14  ldarg.0
0x9d15  ldarg.2
0x9d16  ldarg.s  4
0x9d18  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9d1d  starg.s  2
0x9d1f  ldarg.2
0x9d20  dup
0x9d21  stloc.1
0x9d22  brfalse  loc_A057
0x9d27  volatile.
0x9d29  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000134-1
0x9d2e  brtrue   loc_9E15
0x9d33  ldc.i4.s 0x11
0x9d35  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x9d3a  dup
0x9d3b  ldstr    aUpdate// "Update"
0x9d40  ldc.i4.0
0x9d41  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d46  dup
0x9d47  ldstr    aSystemupdate// "SystemUpdate"
0x9d4c  ldc.i4.1
0x9d4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d52  dup
0x9d53  ldstr    aUpdateoverwrit// "UpdateOverwriteVersion"
0x9d58  ldc.i4.2
0x9d59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d5e  dup
0x9d5f  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x9d64  ldc.i4.3
0x9d65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d6a  dup
0x9d6b  ldstr    aDeleteobject// "DeleteObject"
0x9d70  ldc.i4.4
0x9d71  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d76  dup
0x9d77  ldstr    aRecycle// "Recycle"
0x9d7c  ldc.i4.5
0x9d7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d82  dup
0x9d83  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x9d88  ldc.i4.6
0x9d89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d8e  dup
0x9d8f  ldstr    aSetcommentsdis// "SetCommentsDisabled"
0x9d94  ldc.i4.7
0x9d95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9d9a  dup
0x9d9b  ldstr    aOverridepolicy// "OverridePolicyTip"
0x9da0  ldc.i4.8
0x9da1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9da6  dup
0x9da7  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0x9dac  ldc.i4.s 9
0x9dae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9db3  dup
0x9db4  ldstr    aResetroleinher// "ResetRoleInheritance"
0x9db9  ldc.i4.s 0xA
0x9dbb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9dc0  dup
0x9dc1  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x9dc6  ldc.i4.s 0xB
0x9dc8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9dcd  dup
0x9dce  ldstr    aGetchanges// "GetChanges"
0x9dd3  ldc.i4.s 0xC
0x9dd5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9dda  dup
0x9ddb  ldstr    aSetfieldvalue// "SetFieldValue"
0x9de0  ldc.i4.s 0xD
0x9de2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9de7  dup
0x9de8  ldstr    aParseandsetfie// "ParseAndSetFieldValue"
0x9ded  ldc.i4.s 0xE
0x9def  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9df4  dup
0x9df5  ldstr    aValidateupdate// "ValidateUpdateListItem"
0x9dfa  ldc.i4.s 0xF
0x9dfc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e01  dup
0x9e02  ldstr    aGetfieldvalue// "GetFieldValue"
0x9e07  ldc.i4.s 0x10
0x9e09  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e0e  volatile.
0x9e10  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000134-1
0x9e15  volatile.
0x9e17  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000134-1
0x9e1c  ldloc.1
0x9e1d  ldloca.s 2
0x9e1f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9e24  brfalse  loc_A057
0x9e29  ldloc.2
0x9e2a  switch   loc_9E78, loc_9E94, loc_9EB0, loc_9ECC, loc_9EE8, loc_9F04, loc_9F24, loc_9F3F, loc_9F5B, loc_9F7B, loc_9F96, loc_9FB2, loc_9FCE, loc_9FE9, loc_A005, loc_A021, loc_A03C
0x9e73  br       loc_A057
0x9e78  ldarg.s  5
0x9e7a  ldc.i4.1
0x9e7b  stind.i1
0x9e7c  ldarg.0
0x9e7d  ldstr    aUpdate// "Update"
0x9e82  ldarg.s  4
0x9e84  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9e89  ldloc.0
0x9e8a  ldarg.3
0x9e8b  ldarg.s  4
0x9e8d  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9e92  ldnull
0x9e93  ret
0x9e94  ldarg.s  5
0x9e96  ldc.i4.1
0x9e97  stind.i1
0x9e98  ldarg.0
0x9e99  ldstr    aSystemupdate// "SystemUpdate"
0x9e9e  ldarg.s  4
0x9ea0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9ea5  ldloc.0
0x9ea6  ldarg.3
0x9ea7  ldarg.s  4
0x9ea9  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SystemUpdate_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9eae  ldnull
0x9eaf  ret
0x9eb0  ldarg.s  5
0x9eb2  ldc.i4.1
0x9eb3  stind.i1
0x9eb4  ldarg.0
0x9eb5  ldstr    aUpdateoverwrit// "UpdateOverwriteVersion"
0x9eba  ldarg.s  4
0x9ebc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9ec1  ldloc.0
0x9ec2  ldarg.3
0x9ec3  ldarg.s  4
0x9ec5  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::UpdateOverwriteVersion_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9eca  ldnull
0x9ecb  ret
0x9ecc  ldarg.s  5
0x9ece  ldc.i4.1
0x9ecf  stind.i1
0x9ed0  ldarg.0
0x9ed1  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x9ed6  ldarg.s  4
0x9ed8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9edd  ldloc.0
0x9ede  ldarg.3
0x9edf  ldarg.s  4
0x9ee1  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::UpdateWithFieldValues_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9ee6  ldnull
0x9ee7  ret
0x9ee8  ldarg.s  5
0x9eea  ldc.i4.1
0x9eeb  stind.i1
0x9eec  ldarg.0
0x9eed  ldstr    aDeleteobject// "DeleteObject"
0x9ef2  ldarg.s  4
0x9ef4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9ef9  ldloc.0
0x9efa  ldarg.3
0x9efb  ldarg.s  4
0x9efd  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f02  ldnull
0x9f03  ret
0x9f04  ldarg.s  5
0x9f06  ldc.i4.0
0x9f07  stind.i1
0x9f08  ldarg.0
0x9f09  ldstr    aRecycle// "Recycle"
0x9f0e  ldarg.s  4
0x9f10  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f15  ldloc.0
0x9f16  ldarg.3
0x9f17  ldarg.s  4
0x9f19  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPListItemServerStub::Recycle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f1e  box      [mscorlib]System.Guid
0x9f23  ret
0x9f24  ldarg.s  5
0x9f26  ldc.i4.0
0x9f27  stind.i1
0x9f28  ldarg.0
0x9f29  ldstr    aGetusereffecti// "GetUserEffectivePermissions"
0x9f2e  ldarg.s  4
0x9f30  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f35  ldloc.0
0x9f36  ldarg.3
0x9f37  ldarg.s  4
0x9f39  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPBasePermissions_Client Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetUserEffectivePermissions_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f3e  ret
0x9f3f  ldarg.s  5
0x9f41  ldc.i4.1
0x9f42  stind.i1
0x9f43  ldarg.0
0x9f44  ldstr    aSetcommentsdis// "SetCommentsDisabled"
0x9f49  ldarg.s  4
0x9f4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f50  ldloc.0
0x9f51  ldarg.3
0x9f52  ldarg.s  4
0x9f54  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SetCommentsDisabled_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f59  ldnull
0x9f5a  ret
0x9f5b  ldarg.s  5
0x9f5d  ldc.i4.0
0x9f5e  stind.i1
0x9f5f  ldarg.0
0x9f60  ldstr    aOverridepolicy// "OverridePolicyTip"
0x9f65  ldarg.s  4
0x9f67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f6c  ldloc.0
0x9f6d  ldarg.3
0x9f6e  ldarg.s  4
0x9f70  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPPolicyTipUserActionResult Microsoft.SharePoint.ServerStub.SPListItemServerStub::OverridePolicyTip_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f75  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPPolicyTipUserActionResult
0x9f7a  ret
0x9f7b  ldarg.s  5
0x9f7d  ldc.i4.0
0x9f7e  stind.i1
0x9f7f  ldarg.0
0x9f80  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0x9f85  ldarg.s  4
0x9f87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f8c  ldloc.0
0x9f8d  ldarg.3
0x9f8e  ldarg.s  4
0x9f90  call     string Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetWOPIFrameUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f95  ret
0x9f96  ldarg.s  5
0x9f98  ldc.i4.1
0x9f99  stind.i1
0x9f9a  ldarg.0
0x9f9b  ldstr    aResetroleinher// "ResetRoleInheritance"
0x9fa0  ldarg.s  4
0x9fa2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9fa7  ldloc.0
0x9fa8  ldarg.3
0x9fa9  ldarg.s  4
0x9fab  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::ResetRoleInheritance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9fb0  ldnull
0x9fb1  ret
0x9fb2  ldarg.s  5
0x9fb4  ldc.i4.1
0x9fb5  stind.i1
0x9fb6  ldarg.0
0x9fb7  ldstr    aBreakroleinher// "BreakRoleInheritance"
0x9fbc  ldarg.s  4
0x9fbe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9fc3  ldloc.0
0x9fc4  ldarg.3
0x9fc5  ldarg.s  4
0x9fc7  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::BreakRoleInheritance_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9fcc  ldnull
0x9fcd  ret
0x9fce  ldarg.s  5
0x9fd0  ldc.i4.0
0x9fd1  stind.i1
0x9fd2  ldarg.0
0x9fd3  ldstr    aGetchanges// "GetChanges"
0x9fd8  ldarg.s  4
0x9fda  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9fdf  ldloc.0
0x9fe0  ldarg.3
0x9fe1  ldarg.s  4
0x9fe3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPListItemServerStub::GetChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9fe8  ret
0x9fe9  ldarg.s  5
0x9feb  ldc.i4.1
0x9fec  stind.i1
0x9fed  ldarg.0
0x9fee  ldstr    aSetfieldvalue// "SetFieldValue"
0x9ff3  ldarg.s  4
0x9ff5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9ffa  ldloc.0
0x9ffb  ldarg.3
0x9ffc  ldarg.s  4
0x9ffe  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::SetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa003  ldnull
0xa004  ret
0xa005  ldarg.s  5
0xa007  ldc.i4.1
0xa008  stind.i1
0xa009  ldarg.0
0xa00a  ldstr    aParseandsetfie// "ParseAndSetFieldValue"
0xa00f  ldarg.s  4
0xa011  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa016  ldloc.0
0xa017  ldarg.3
0xa018  ldarg.s  4
0xa01a  call     void Microsoft.SharePoint.ServerStub.SPListItemServerStub::ParseAndSetFieldValue_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa01f  ldnull
0xa020  ret
0xa021  ldarg.s  5
0xa023  ldc.i4.0
  ... truncated ...
```
