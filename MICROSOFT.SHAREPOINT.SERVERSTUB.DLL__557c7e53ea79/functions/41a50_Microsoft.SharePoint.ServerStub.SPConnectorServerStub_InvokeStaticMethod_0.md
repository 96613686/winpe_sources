# Microsoft.SharePoint.ServerStub.SPConnectorServerStub::InvokeStaticMethod_0

- ea: `0x41a50`
- end: `0x41ce5`
- name: `Microsoft.SharePoint.ServerStub.SPConnectorServerStub::InvokeStaticMethod_0`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x41720`
- `0x41750`
- `0x41760`
- `0x41780`
- `0x417b0`
- `0x417e0`
- `0x41830`
- `0x41880`
- `0x418d0`
- `0x41910`
- `0x41950`
- `0x41980`
- `0x419b0`
- `0x419f0`
- `0x41a50`

## string_xrefs

- `0x41a84`: `DeleteListItem`
- `0x41b93`: `DeleteListItem`
- `0x41acc`: `GetUpdatedListItems`
- `0x41c23`: `GetUpdatedListItems`
- `0x41ad8`: `GetDeletedListItems`
- `0x41c3b`: `GetDeletedListItems`
- `0x41b0a`: `CreateListItem`
- `0x41c9b`: `CreateListItem`
- `0x41b17`: `UpdateListItem`
- `0x41cb3`: `UpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0x41a50  ldarg.3
0x41a51  brtrue.s loc_41A5E
0x41a53  ldstr    aProxycontext// "proxyContext"
0x41a58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41a5d  throw
0x41a5e  ldarg.0
0x41a5f  ldarg.1
0x41a60  ldarg.3
0x41a61  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41a66  starg.s  1
0x41a68  ldarg.1
0x41a69  dup
0x41a6a  stloc.0
0x41a6b  brfalse  loc_41CDE
0x41a70  volatile.
0x41a72  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c52-1
0x41a77  brtrue   loc_41B37
0x41a7c  ldc.i4.s 0xE
0x41a7e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x41a83  dup
0x41a84  ldstr    aDeletelistitem// "DeleteListItem"
0x41a89  ldc.i4.0
0x41a8a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41a8f  dup
0x41a90  ldstr    aGettables// "GetTables"
0x41a95  ldc.i4.1
0x41a96  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41a9b  dup
0x41a9c  ldstr    aGettablemetada// "GetTableMetadata"
0x41aa1  ldc.i4.2
0x41aa2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41aa7  dup
0x41aa8  ldstr    aGetlistitem// "GetListItem"
0x41aad  ldc.i4.3
0x41aae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41ab3  dup
0x41ab4  ldstr    aGetlistitems// "GetListItems"
0x41ab9  ldc.i4.4
0x41aba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41abf  dup
0x41ac0  ldstr    aGetnewlistitem// "GetNewListItems"
0x41ac5  ldc.i4.5
0x41ac6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41acb  dup
0x41acc  ldstr    aGetupdatedlist// "GetUpdatedListItems"
0x41ad1  ldc.i4.6
0x41ad2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41ad7  dup
0x41ad8  ldstr    aGetdeletedlist// "GetDeletedListItems"
0x41add  ldc.i4.7
0x41ade  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41ae3  dup
0x41ae4  ldstr    aGetentityvalue// "GetEntityValues"
0x41ae9  ldc.i4.8
0x41aea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41aef  dup
0x41af0  ldstr    aResolveentityv// "ResolveEntityValue"
0x41af5  ldc.i4.s 9
0x41af7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41afc  dup
0x41afd  ldstr    aGetentities// "GetEntities"
0x41b02  ldc.i4.s 0xA
0x41b04  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41b09  dup
0x41b0a  ldstr    aCreatelistitem// "CreateListItem"
0x41b0f  ldc.i4.s 0xB
0x41b11  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41b16  dup
0x41b17  ldstr    aUpdatelistitem// "UpdateListItem"
0x41b1c  ldc.i4.s 0xC
0x41b1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41b23  dup
0x41b24  ldstr    aSetapprovalsta// "SetApprovalStatus"
0x41b29  ldc.i4.s 0xD
0x41b2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41b30  volatile.
0x41b32  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c52-1
0x41b37  volatile.
0x41b39  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c52-1
0x41b3e  ldloc.0
0x41b3f  ldloca.s 1
0x41b41  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x41b46  brfalse  loc_41CDE
0x41b4b  ldloc.1
0x41b4c  switch   loc_41B8E, loc_41BA6, loc_41BBE, loc_41BD6, loc_41BEE, loc_41C06, loc_41C1E, loc_41C36, loc_41C4E, loc_41C66, loc_41C7E, loc_41C96, loc_41CAE, loc_41CC6
0x41b89  br       loc_41CDE
0x41b8e  ldarg.s  4
0x41b90  ldc.i4.0
0x41b91  stind.i1
0x41b92  ldarg.0
0x41b93  ldstr    aDeletelistitem// "DeleteListItem"
0x41b98  ldarg.3
0x41b99  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41b9e  ldarg.2
0x41b9f  ldarg.3
0x41ba0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::DeleteListItem_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41ba5  ret
0x41ba6  ldarg.s  4
0x41ba8  ldc.i4.0
0x41ba9  stind.i1
0x41baa  ldarg.0
0x41bab  ldstr    aGettables// "GetTables"
0x41bb0  ldarg.3
0x41bb1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41bb6  ldarg.2
0x41bb7  ldarg.3
0x41bb8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetTables_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41bbd  ret
0x41bbe  ldarg.s  4
0x41bc0  ldc.i4.0
0x41bc1  stind.i1
0x41bc2  ldarg.0
0x41bc3  ldstr    aGettablemetada// "GetTableMetadata"
0x41bc8  ldarg.3
0x41bc9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41bce  ldarg.2
0x41bcf  ldarg.3
0x41bd0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetTableMetadata_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41bd5  ret
0x41bd6  ldarg.s  4
0x41bd8  ldc.i4.0
0x41bd9  stind.i1
0x41bda  ldarg.0
0x41bdb  ldstr    aGetlistitem// "GetListItem"
0x41be0  ldarg.3
0x41be1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41be6  ldarg.2
0x41be7  ldarg.3
0x41be8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetListItem_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41bed  ret
0x41bee  ldarg.s  4
0x41bf0  ldc.i4.0
0x41bf1  stind.i1
0x41bf2  ldarg.0
0x41bf3  ldstr    aGetlistitems// "GetListItems"
0x41bf8  ldarg.3
0x41bf9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41bfe  ldarg.2
0x41bff  ldarg.3
0x41c00  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetListItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c05  ret
0x41c06  ldarg.s  4
0x41c08  ldc.i4.0
0x41c09  stind.i1
0x41c0a  ldarg.0
0x41c0b  ldstr    aGetnewlistitem// "GetNewListItems"
0x41c10  ldarg.3
0x41c11  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c16  ldarg.2
0x41c17  ldarg.3
0x41c18  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetNewListItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c1d  ret
0x41c1e  ldarg.s  4
0x41c20  ldc.i4.0
0x41c21  stind.i1
0x41c22  ldarg.0
0x41c23  ldstr    aGetupdatedlist// "GetUpdatedListItems"
0x41c28  ldarg.3
0x41c29  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c2e  ldarg.2
0x41c2f  ldarg.3
0x41c30  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetUpdatedListItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c35  ret
0x41c36  ldarg.s  4
0x41c38  ldc.i4.0
0x41c39  stind.i1
0x41c3a  ldarg.0
0x41c3b  ldstr    aGetdeletedlist// "GetDeletedListItems"
0x41c40  ldarg.3
0x41c41  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c46  ldarg.2
0x41c47  ldarg.3
0x41c48  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetDeletedListItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c4d  ret
0x41c4e  ldarg.s  4
0x41c50  ldc.i4.0
0x41c51  stind.i1
0x41c52  ldarg.0
0x41c53  ldstr    aGetentityvalue// "GetEntityValues"
0x41c58  ldarg.3
0x41c59  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c5e  ldarg.2
0x41c5f  ldarg.3
0x41c60  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetEntityValues_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c65  ret
0x41c66  ldarg.s  4
0x41c68  ldc.i4.0
0x41c69  stind.i1
0x41c6a  ldarg.0
0x41c6b  ldstr    aResolveentityv// "ResolveEntityValue"
0x41c70  ldarg.3
0x41c71  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c76  ldarg.2
0x41c77  ldarg.3
0x41c78  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::ResolveEntityValue_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c7d  ret
0x41c7e  ldarg.s  4
0x41c80  ldc.i4.0
0x41c81  stind.i1
0x41c82  ldarg.0
0x41c83  ldstr    aGetentities// "GetEntities"
0x41c88  ldarg.3
0x41c89  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41c8e  ldarg.2
0x41c8f  ldarg.3
0x41c90  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetEntities_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41c95  ret
0x41c96  ldarg.s  4
0x41c98  ldc.i4.0
0x41c99  stind.i1
0x41c9a  ldarg.0
0x41c9b  ldstr    aCreatelistitem// "CreateListItem"
0x41ca0  ldarg.3
0x41ca1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41ca6  ldarg.2
0x41ca7  ldarg.3
0x41ca8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::CreateListItem_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41cad  ret
0x41cae  ldarg.s  4
0x41cb0  ldc.i4.0
0x41cb1  stind.i1
0x41cb2  ldarg.0
0x41cb3  ldstr    aUpdatelistitem// "UpdateListItem"
0x41cb8  ldarg.3
0x41cb9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41cbe  ldarg.2
0x41cbf  ldarg.3
0x41cc0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::UpdateListItem_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41cc5  ret
0x41cc6  ldarg.s  4
0x41cc8  ldc.i4.0
0x41cc9  stind.i1
0x41cca  ldarg.0
0x41ccb  ldstr    aSetapprovalsta// "SetApprovalStatus"
0x41cd0  ldarg.3
0x41cd1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41cd6  ldarg.2
0x41cd7  ldarg.3
0x41cd8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::SetApprovalStatus_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41cdd  ret
0x41cde  ldarg.1
0x41cdf  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x41ce4  throw
```
