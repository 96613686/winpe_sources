# Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::GetProperty

- ea: `0x6d460`
- end: `0x6d754`
- name: `Microsoft.SharePoint.ServerStub.SPObjectSharingInformationServerStub::GetProperty`
- size: `756`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x6d460`

## string_xrefs

- `0x6d4b7`: `AnonymousEditLink`
- `0x6d5e4`: `AnonymousEditLink`
- `0x6d4c3`: `AnonymousViewLink`
- `0x6d5f7`: `AnonymousViewLink`
- `0x6d4f3`: `HasPendingAccessRequests`
- `0x6d652`: `HasPendingAccessRequests`
- `0x6d53d`: `IsSharedWithSecurityGroup`
- `0x6d6e2`: `IsSharedWithSecurityGroup`
- `0x6d54a`: `PendingAccessRequestsLink`
- `0x6d6fa`: `PendingAccessRequestsLink`
- `0x6d564`: `SharingLinks`
- `0x6d720`: `SharingLinks`

## pseudocode

```c

```

## disassembly

```asm
0x6d460  ldarg.2
0x6d461  brtrue.s loc_6D46E
0x6d463  ldstr    aPropname// "propName"
0x6d468  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6d46d  throw
0x6d46e  ldarg.3
0x6d46f  brtrue.s loc_6D47C
0x6d471  ldstr    aProxycontext// "proxyContext"
0x6d476  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6d47b  throw
0x6d47c  ldarg.1
0x6d47d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation
0x6d482  stloc.0
0x6d483  ldloc.0
0x6d484  brtrue.s loc_6D491
0x6d486  ldstr    aTarget// "target"
0x6d48b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6d490  throw
0x6d491  ldarg.0
0x6d492  ldarg.2
0x6d493  ldarg.3
0x6d494  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d499  starg.s  2
0x6d49b  ldarg.2
0x6d49c  dup
0x6d49d  stloc.1
0x6d49e  brfalse  loc_6D74A
0x6d4a3  volatile.
0x6d4a5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001339-1
0x6d4aa  brtrue   loc_6D584
0x6d4af  ldc.i4.s 0x10
0x6d4b1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6d4b6  dup
0x6d4b7  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6d4bc  ldc.i4.0
0x6d4bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4c2  dup
0x6d4c3  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6d4c8  ldc.i4.1
0x6d4c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4ce  dup
0x6d4cf  ldstr    aCanbeshared// "CanBeShared"
0x6d4d4  ldc.i4.2
0x6d4d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4da  dup
0x6d4db  ldstr    aCanbeunshared// "CanBeUnshared"
0x6d4e0  ldc.i4.3
0x6d4e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4e6  dup
0x6d4e7  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6d4ec  ldc.i4.4
0x6d4ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4f2  dup
0x6d4f3  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6d4f8  ldc.i4.5
0x6d4f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d4fe  dup
0x6d4ff  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6d504  ldc.i4.6
0x6d505  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d50a  dup
0x6d50b  ldstr    aIsfolder// "IsFolder"
0x6d510  ldc.i4.7
0x6d511  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d516  dup
0x6d517  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6d51c  ldc.i4.8
0x6d51d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d522  dup
0x6d523  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6d528  ldc.i4.s 9
0x6d52a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d52f  dup
0x6d530  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6d535  ldc.i4.s 0xA
0x6d537  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d53c  dup
0x6d53d  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6d542  ldc.i4.s 0xB
0x6d544  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d549  dup
0x6d54a  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6d54f  ldc.i4.s 0xC
0x6d551  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d556  dup
0x6d557  ldstr    aSharedwithuser_0// "SharedWithUsersCollection"
0x6d55c  ldc.i4.s 0xD
0x6d55e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d563  dup
0x6d564  ldstr    aSharinglinks// "SharingLinks"
0x6d569  ldc.i4.s 0xE
0x6d56b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d570  dup
0x6d571  ldstr    aTotalfilecount// "TotalFileCount"
0x6d576  ldc.i4.s 0xF
0x6d578  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d57d  volatile.
0x6d57f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001339-1
0x6d584  volatile.
0x6d586  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001339-1
0x6d58b  ldloc.1
0x6d58c  ldloca.s 2
0x6d58e  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6d593  brfalse  loc_6D74A
0x6d598  ldloc.2
0x6d599  switch   loc_6D5E3, loc_6D5F6, loc_6D609, loc_6D621, loc_6D639, loc_6D651, loc_6D669, loc_6D681, loc_6D699, loc_6D6B1, loc_6D6C9, loc_6D6E1, loc_6D6F9, loc_6D70C, loc_6D71F, loc_6D732
0x6d5de  br       loc_6D74A
0x6d5e3  ldarg.0
0x6d5e4  ldstr    aAnonymouseditl// "AnonymousEditLink"
0x6d5e9  ldarg.3
0x6d5ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d5ef  ldloc.0
0x6d5f0  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousEditLink()
0x6d5f5  ret
0x6d5f6  ldarg.0
0x6d5f7  ldstr    aAnonymousviewl// "AnonymousViewLink"
0x6d5fc  ldarg.3
0x6d5fd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d602  ldloc.0
0x6d603  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_AnonymousViewLink()
0x6d608  ret
0x6d609  ldarg.0
0x6d60a  ldstr    aCanbeshared// "CanBeShared"
0x6d60f  ldarg.3
0x6d610  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d615  ldloc.0
0x6d616  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeShared()
0x6d61b  box      [mscorlib]System.Boolean
0x6d620  ret
0x6d621  ldarg.0
0x6d622  ldstr    aCanbeunshared// "CanBeUnshared"
0x6d627  ldarg.3
0x6d628  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d62d  ldloc.0
0x6d62e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanBeUnshared()
0x6d633  box      [mscorlib]System.Boolean
0x6d638  ret
0x6d639  ldarg.0
0x6d63a  ldstr    aCanmanagepermi// "CanManagePermissions"
0x6d63f  ldarg.3
0x6d640  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d645  ldloc.0
0x6d646  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_CanManagePermissions()
0x6d64b  box      [mscorlib]System.Boolean
0x6d650  ret
0x6d651  ldarg.0
0x6d652  ldstr    aHaspendingacce// "HasPendingAccessRequests"
0x6d657  ldarg.3
0x6d658  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d65d  ldloc.0
0x6d65e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPendingAccessRequests()
0x6d663  box      [mscorlib]System.Boolean
0x6d668  ret
0x6d669  ldarg.0
0x6d66a  ldstr    aHaspermissionl// "HasPermissionLevels"
0x6d66f  ldarg.3
0x6d670  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d675  ldloc.0
0x6d676  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_HasPermissionLevels()
0x6d67b  box      [mscorlib]System.Boolean
0x6d680  ret
0x6d681  ldarg.0
0x6d682  ldstr    aIsfolder// "IsFolder"
0x6d687  ldarg.3
0x6d688  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d68d  ldloc.0
0x6d68e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsFolder()
0x6d693  box      [mscorlib]System.Boolean
0x6d698  ret
0x6d699  ldarg.0
0x6d69a  ldstr    aIssharedwithcu// "IsSharedWithCurrentUser"
0x6d69f  ldarg.3
0x6d6a0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d6a5  ldloc.0
0x6d6a6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithCurrentUser()
0x6d6ab  box      [mscorlib]System.Boolean
0x6d6b0  ret
0x6d6b1  ldarg.0
0x6d6b2  ldstr    aIssharedwithgu// "IsSharedWithGuest"
0x6d6b7  ldarg.3
0x6d6b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d6bd  ldloc.0
0x6d6be  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithGuest()
0x6d6c3  box      [mscorlib]System.Boolean
0x6d6c8  ret
0x6d6c9  ldarg.0
0x6d6ca  ldstr    aIssharedwithma// "IsSharedWithMany"
0x6d6cf  ldarg.3
0x6d6d0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d6d5  ldloc.0
0x6d6d6  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithMany()
0x6d6db  box      [mscorlib]System.Boolean
0x6d6e0  ret
0x6d6e1  ldarg.0
0x6d6e2  ldstr    aIssharedwithse// "IsSharedWithSecurityGroup"
0x6d6e7  ldarg.3
0x6d6e8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d6ed  ldloc.0
0x6d6ee  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_IsSharedWithSecurityGroup()
0x6d6f3  box      [mscorlib]System.Boolean
0x6d6f8  ret
0x6d6f9  ldarg.0
0x6d6fa  ldstr    aPendingaccessr// "PendingAccessRequestsLink"
0x6d6ff  ldarg.3
0x6d700  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d705  ldloc.0
0x6d706  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_PendingAccessRequestsLink()
0x6d70b  ret
0x6d70c  ldarg.0
0x6d70d  ldstr    aSharedwithuser_0// "SharedWithUsersCollection"
0x6d712  ldarg.3
0x6d713  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d718  ldloc.0
0x6d719  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformationUserCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_SharedWithUsersCollection()
0x6d71e  ret
0x6d71f  ldarg.0
0x6d720  ldstr    aSharinglinks// "SharingLinks"
0x6d725  ldarg.3
0x6d726  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d72b  ldloc.0
0x6d72c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkInfo> [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_SharingLinks()
0x6d731  ret
0x6d732  ldarg.0
0x6d733  ldstr    aTotalfilecount// "TotalFileCount"
0x6d738  ldarg.3
0x6d739  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d73e  ldloc.0
0x6d73f  callvirt instance unsigned int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPObjectSharingInformation::get_TotalFileCount()
0x6d744  box      [mscorlib]System.UInt64
0x6d749  ret
0x6d74a  ldarg.0
0x6d74b  ldarg.1
0x6d74c  ldarg.2
0x6d74d  ldarg.3
0x6d74e  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d753  ret
```
