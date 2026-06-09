# System.Deployment.Application.ComponentStore::CommitApplication

- ea: `0xe360`
- end: `0xe3c9`
- name: `System.Deployment.Application.ComponentStore::CommitApplication`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1f1c0`

## callees

- `0xe360`
- `0xef90`
- `0xfb30`
- `0x14700`
- `0x23020`
- `0x28490`

## string_xrefs

- `0xe3b5`: `Ex_InplaceUpdateOfApplicationAttempted`

## pseudocode

```c

```

## disassembly

```asm
0xe360  ldarg.0
0xe361  newobj   instance void StoreTransactionContext::.ctor(class System.Deployment.Application.ComponentStore compStore)
0xe366  stloc.0
0xe367  ldarg.0
0xe368  ldloc.0
0xe369  ldarg.1
0xe36a  ldarg.2
0xe36b  call     instance void System.Deployment.Application.ComponentStore::PrepareCommitApplication(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0xe370  ldarg.0
0xe371  ldloc.0
0xe372  ldarg.1
0xe373  call     instance void System.Deployment.Application.ComponentStore::SubmitStoreTransactionCheckQuota(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState)
0xe378  leave.s  loc_E384
0xe37a  ldloc.0
0xe37b  brfalse.s loc_E383
0xe37d  ldloc.0
0xe37e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe383  endfinally
0xe384  leave.s  loc_E3C8
0xe386  stloc.1
0xe387  ldloc.1
0xe388  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xe38d  ldc.i4   0x80070070
0xe392  bne.un.s loc_E3A7
0xe394  ldc.i4.s 0xA
0xe396  ldstr    aExStoreoperati// "Ex_StoreOperationFailed"
0xe39b  call     string System.Deployment.Application.Resources::GetString(string s)
0xe3a0  ldloc.1
0xe3a1  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xe3a6  throw
0xe3a7  ldloc.1
0xe3a8  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xe3ad  ldc.i4   0x8007051A
0xe3b2  bne.un.s loc_E3C6
0xe3b4  ldc.i4.2
0xe3b5  ldstr    aExInplaceupdat// "Ex_InplaceUpdateOfApplicationAttempted"
0xe3ba  call     string System.Deployment.Application.Resources::GetString(string s)
0xe3bf  ldloc.1
0xe3c0  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xe3c5  throw
0xe3c6  rethrow
0xe3c8  ret
```
