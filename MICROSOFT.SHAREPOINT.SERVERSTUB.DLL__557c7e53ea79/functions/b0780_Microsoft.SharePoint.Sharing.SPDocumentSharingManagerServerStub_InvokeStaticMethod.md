# Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::InvokeStaticMethod

- ea: `0xb0780`
- end: `0xb08d6`
- name: `Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::InvokeStaticMethod`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0xb0640`
- `0xb0660`
- `0xb0680`
- `0xb06a0`
- `0xb0740`
- `0xb0760`
- `0xb0780`

## string_xrefs

- `0xb07d4`: `UpdateDocumentSharingInfo`
- `0xb088c`: `UpdateDocumentSharingInfo`
- `0xb07e0`: `RemoveItemsFromSharedWithMeView`
- `0xb08a4`: `RemoveItemsFromSharedWithMeView`
- `0xb07ec`: `RemoveItemsFromSharedWithMeViewByPath`
- `0xb08bc`: `RemoveItemsFromSharedWithMeViewByPath`

## pseudocode

```c

```

## disassembly

```asm
0xb0780  ldarg.3
0xb0781  brtrue.s loc_B078E
0xb0783  ldstr    aProxycontext// "proxyContext"
0xb0788  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb078d  throw
0xb078e  ldarg.0
0xb078f  ldarg.1
0xb0790  ldarg.3
0xb0791  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0796  starg.s  1
0xb0798  ldarg.1
0xb0799  dup
0xb079a  stloc.0
0xb079b  brfalse  loc_B08CF
0xb07a0  volatile.
0xb07a2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cba-1
0xb07a7  brtrue.s loc_B07FE
0xb07a9  ldc.i4.6
0xb07aa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xb07af  dup
0xb07b0  ldstr    aGetroledefinit// "GetRoleDefinition"
0xb07b5  ldc.i4.0
0xb07b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07bb  dup
0xb07bc  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0xb07c1  ldc.i4.1
0xb07c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07c7  dup
0xb07c8  ldstr    aCanmembershare// "CanMemberShare"
0xb07cd  ldc.i4.2
0xb07ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07d3  dup
0xb07d4  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb07d9  ldc.i4.3
0xb07da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07df  dup
0xb07e0  ldstr    aRemoveitemsfro// "RemoveItemsFromSharedWithMeView"
0xb07e5  ldc.i4.4
0xb07e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07eb  dup
0xb07ec  ldstr    aRemoveitemsfro_0// "RemoveItemsFromSharedWithMeViewByPath"
0xb07f1  ldc.i4.5
0xb07f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xb07f7  volatile.
0xb07f9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cba-1
0xb07fe  volatile.
0xb0800  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001cba-1
0xb0805  ldloc.0
0xb0806  ldloca.s 1
0xb0808  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xb080d  brfalse  loc_B08CF
0xb0812  ldloc.1
0xb0813  switch   loc_B0835, loc_B084D, loc_B086A, loc_B0887, loc_B089F, loc_B08B7
0xb0830  br       loc_B08CF
0xb0835  ldarg.s  4
0xb0837  ldc.i4.0
0xb0838  stind.i1
0xb0839  ldarg.0
0xb083a  ldstr    aGetroledefinit// "GetRoleDefinition"
0xb083f  ldarg.3
0xb0840  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0845  ldarg.2
0xb0846  ldarg.3
0xb0847  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPRoleDefinition Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::GetRoleDefinition_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb084c  ret
0xb084d  ldarg.s  4
0xb084f  ldc.i4.0
0xb0850  stind.i1
0xb0851  ldarg.0
0xb0852  ldstr    aIsdocumentshar// "IsDocumentSharingEnabled"
0xb0857  ldarg.3
0xb0858  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb085d  ldarg.2
0xb085e  ldarg.3
0xb085f  call     bool Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::IsDocumentSharingEnabled_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0864  box      [mscorlib]System.Boolean
0xb0869  ret
0xb086a  ldarg.s  4
0xb086c  ldc.i4.0
0xb086d  stind.i1
0xb086e  ldarg.0
0xb086f  ldstr    aCanmembershare// "CanMemberShare"
0xb0874  ldarg.3
0xb0875  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb087a  ldarg.2
0xb087b  ldarg.3
0xb087c  call     bool Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::CanMemberShare_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb0881  box      [mscorlib]System.Boolean
0xb0886  ret
0xb0887  ldarg.s  4
0xb0889  ldc.i4.0
0xb088a  stind.i1
0xb088b  ldarg.0
0xb088c  ldstr    aUpdatedocument// "UpdateDocumentSharingInfo"
0xb0891  ldarg.3
0xb0892  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb0897  ldarg.2
0xb0898  ldarg.3
0xb0899  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.UserSharingResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::UpdateDocumentSharingInfo_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb089e  ret
0xb089f  ldarg.s  4
0xb08a1  ldc.i4.0
0xb08a2  stind.i1
0xb08a3  ldarg.0
0xb08a4  ldstr    aRemoveitemsfro// "RemoveItemsFromSharedWithMeView"
0xb08a9  ldarg.3
0xb08aa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb08af  ldarg.2
0xb08b0  ldarg.3
0xb08b1  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::RemoveItemsFromSharedWithMeView_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb08b6  ret
0xb08b7  ldarg.s  4
0xb08b9  ldc.i4.0
0xb08ba  stind.i1
0xb08bb  ldarg.0
0xb08bc  ldstr    aRemoveitemsfro_0// "RemoveItemsFromSharedWithMeViewByPath"
0xb08c1  ldarg.3
0xb08c2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb08c7  ldarg.2
0xb08c8  ldarg.3
0xb08c9  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Sharing.SharedWithMeViewItemRemovalResult> Microsoft.SharePoint.Sharing.SPDocumentSharingManagerServerStub::RemoveItemsFromSharedWithMeViewByPath_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb08ce  ret
0xb08cf  ldarg.1
0xb08d0  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb08d5  throw
```
