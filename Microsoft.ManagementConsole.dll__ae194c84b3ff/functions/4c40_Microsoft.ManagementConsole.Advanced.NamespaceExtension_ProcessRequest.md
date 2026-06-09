# Microsoft.ManagementConsole.Advanced.NamespaceExtension::ProcessRequest

- ea: `0x4c40`
- end: `0x4c95`
- name: `Microsoft.ManagementConsole.Advanced.NamespaceExtension::ProcessRequest`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4970`
- `0x4c40`
- `0x4cc0`
- `0x7250`
- `0x73b0`

## pseudocode

```c

```

## disassembly

```asm
0x4c40  ldarg.1
0x4c41  brtrue.s loc_4C4E
0x4c43  ldstr    aRequest// "request"
0x4c48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4c4d  throw
0x4c4e  ldarg.1
0x4c4f  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestInfo [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request::get_RequestInfo()
0x4c54  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PersistenceKeyRequestInfo
0x4c59  brfalse.s loc_4C8D
0x4c5b  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PersistenceKeyRetrievalCompletedResponse::.ctor()
0x4c60  stloc.0
0x4c61  ldarg.1
0x4c62  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request::get_RequestStatus()
0x4c67  stloc.1
0x4c68  ldloc.1
0x4c69  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x4c6e  stloc.2
0x4c6f  ldarg.0
0x4c70  callvirt instance string Microsoft.ManagementConsole.Advanced.NamespaceExtension::OnRetrievePersistenceKey()
0x4c75  stloc.3
0x4c76  ldloc.0
0x4c77  ldloc.3
0x4c78  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PersistenceKeyRetrievalCompletedResponse::set_PersistenceKey(string)
0x4c7d  ldloc.1
0x4c7e  ldloc.0
0x4c7f  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0x4c84  leave.s  loc_4C94
0x4c86  ldloc.2
0x4c87  callvirt instance void Microsoft.ManagementConsole.Status::Close()
0x4c8c  endfinally
0x4c8d  ldarg.0
0x4c8e  ldarg.1
0x4c8f  call     instance void Microsoft.ManagementConsole.NamespaceSnapInBase::ProcessRequest(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Request request)
0x4c94  ret
```
