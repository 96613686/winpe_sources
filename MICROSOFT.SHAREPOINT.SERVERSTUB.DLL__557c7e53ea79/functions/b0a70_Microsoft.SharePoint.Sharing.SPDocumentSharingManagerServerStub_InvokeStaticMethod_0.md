# Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::InvokeStaticMethod_0

- ea: `0xb0a70`
- end: `0xb0bc6`
- name: `Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::InvokeStaticMethod_0`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb0940`
- `0xb0960`
- `0xb0980`
- `0xb09a0`
- `0xb0a30`
- `0xb0a50`
- `0xb0a70`

## string_xrefs

- `0xb0ac4`: `UpdateDocumentSharingInfo`
- `0xb0b7c`: `UpdateDocumentSharingInfo`
- `0xb0ad0`: `RemoveItemsFromSharedWithMeView`
- `0xb0b94`: `RemoveItemsFromSharedWithMeView`
- `0xb0adc`: `RemoveItemsFromSharedWithMeViewByPath`
- `0xb0bac`: `RemoveItemsFromSharedWithMeViewByPath`

## pseudocode

```c

```

## disassembly

```asm
0xb0a70  ldarg.3
0xb0a71  brtrue.s loc_B0A7E
0xb0a73  ldstr    aProxycontext// "proxyContext"
0xb0a78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb0a7d  throw
0xb0a7e  ldarg.0
0xb0a7f  ldarg.1
0xb0a80  ldarg.3
0xb0a81  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0a86  starg.s  1
0xb0a88  ldarg.1
0xb0a89  dup
0xb0a8a  stloc.0
0xb0a8b  brfalse  loc_B0BBF
0xb0a90  volatile.
0xb0a92  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cc4-1
0xb0a97  brtrue.s loc_B0AEE
0xb0a99  ldc.i4.6
0xb0a9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb0a9f  dup
0xb0aa0  ldstr    aGetroledefinit// "GetRoleDefinition"
0xb0aa5  ldc.i4.0
0xb0aa6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0aab  dup
0xb0aac  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0xb0ab1  ldc.i4.1
0xb0ab2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0ab7  dup
0xb0ab8  ldstr    aCanmembershare// "CanMemberShare"
0xb0abd  ldc.i4.2
0xb0abe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0ac3  dup
0xb0ac4  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb0ac9  ldc.i4.3
0xb0aca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0acf  dup
0xb0ad0  ldstr    aRemoveitemsfro// "RemoveItemsFromSharedWithMeView"
0xb0ad5  ldc.i4.4
0xb0ad6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0adb  dup
0xb0adc  ldstr    aRemoveitemsfro_0// "RemoveItemsFromSharedWithMeViewByPath"
0xb0ae1  ldc.i4.5
0xb0ae2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb0ae7  volatile.
0xb0ae9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cc4-1
0xb0aee  volatile.
0xb0af0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cc4-1
0xb0af5  ldloc.0
0xb0af6  ldloca.s 1
0xb0af8  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb0afd  brfalse  loc_B0BBF
0xb0b02  ldloc.1
0xb0b03  switch   loc_B0B25, loc_B0B3D, loc_B0B5A, loc_B0B77, loc_B0B8F, loc_B0BA7
0xb0b20  br       loc_B0BBF
0xb0b25  ldarg.s  4
0xb0b27  ldc.i4.0
0xb0b28  stind.i1
0xb0b29  ldarg.0
0xb0b2a  ldstr    aGetroledefinit// "GetRoleDefinition"
0xb0b2f  ldarg.3
0xb0b30  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0b35  ldarg.2
0xb0b36  ldarg.3
0xb0b37  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::GetRoleDefinition_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0b3c  ret
0xb0b3d  ldarg.s  4
0xb0b3f  ldc.i4.0
0xb0b40  stind.i1
0xb0b41  ldarg.0
0xb0b42  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0xb0b47  ldarg.3
0xb0b48  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0b4d  ldarg.2
0xb0b4e  ldarg.3
0xb0b4f  call     bool Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::IsDocumentSharingEnabled_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0b54  box      [mscorlib]System.Boolean
0xb0b59  ret
0xb0b5a  ldarg.s  4
0xb0b5c  ldc.i4.0
0xb0b5d  stind.i1
0xb0b5e  ldarg.0
0xb0b5f  ldstr    aCanmembershare// "CanMemberShare"
0xb0b64  ldarg.3
0xb0b65  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0b6a  ldarg.2
0xb0b6b  ldarg.3
0xb0b6c  call     bool Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::CanMemberShare_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0b71  box      [mscorlib]System.Boolean
0xb0b76  ret
0xb0b77  ldarg.s  4
0xb0b79  ldc.i4.0
0xb0b7a  stind.i1
0xb0b7b  ldarg.0
0xb0b7c  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb0b81  ldarg.3
0xb0b82  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0b87  ldarg.2
0xb0b88  ldarg.3
0xb0b89  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.UserSharingResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::UpdateDocumentSharingInfo_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0b8e  ret
0xb0b8f  ldarg.s  4
0xb0b91  ldc.i4.0
0xb0b92  stind.i1
0xb0b93  ldarg.0
0xb0b94  ldstr    aRemoveitemsfro// "RemoveItemsFromSharedWithMeView"
0xb0b99  ldarg.3
0xb0b9a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0b9f  ldarg.2
0xb0ba0  ldarg.3
0xb0ba1  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::RemoveItemsFromSharedWithMeView_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0ba6  ret
0xb0ba7  ldarg.s  4
0xb0ba9  ldc.i4.0
0xb0baa  stind.i1
0xb0bab  ldarg.0
0xb0bac  ldstr    aRemoveitemsfro_0// "RemoveItemsFromSharedWithMeViewByPath"
0xb0bb1  ldarg.3
0xb0bb2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0bb7  ldarg.2
0xb0bb8  ldarg.3
0xb0bb9  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::RemoveItemsFromSharedWithMeViewByPath_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0bbe  ret
0xb0bbf  ldarg.1
0xb0bc0  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb0bc5  throw
```
