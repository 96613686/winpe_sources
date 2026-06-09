# System.Deployment.Application.ComponentStore::SubmitStoreTransaction

- ea: `0xfa50`
- end: `0xfb21`
- name: `System.Deployment.Application.ComponentStore::SubmitStoreTransaction`
- size: `209`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xe200`
- `0xe470`
- `0xe4c0`
- `0xfb30`
- `0x286e0`
- `0x28ab0`

## callees

- `0x40`
- `0x2900`
- `0x29d0`
- `0x2fa0`
- `0x31b0`
- `0x3d10`
- `0xfa50`
- `0x14700`
- `0x17d80`
- `0x1ecd0`
- `0x22b20`
- `0x23020`

## string_xrefs

- `0xfaad`: `Ex_TransactDirectoryNotFoundException`

## pseudocode

```c

```

## disassembly

```asm
0xfa50  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0xfa55  ldc.i4   0x1F90
0xfa5a  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0xfa5f  pop
0xfa60  ldarg.1
0xfa61  ldc.i4.0
0xfa62  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationScavenge::.ctor(bool Light)
0xfa67  callvirt instance void System.Deployment.Internal.Isolation.StoreTransaction::Add(valuetype System.Deployment.Internal.Isolation.StoreOperationScavenge o)
0xfa6c  ldarg.1
0xfa6d  callvirt instance valuetype System.Deployment.Internal.Isolation.StoreTransactionOperation[] System.Deployment.Internal.Isolation.StoreTransaction::get_Operations()
0xfa72  stloc.0
0xfa73  ldloc.0
0xfa74  ldlen
0xfa75  brfalse  loc_FB20
0xfa7a  ldloc.0
0xfa7b  ldlen
0xfa7c  conv.i4
0xfa7d  newarr   [mscorlib]System.UInt32
0xfa82  stloc.1
0xfa83  ldloc.0
0xfa84  ldlen
0xfa85  conv.i4
0xfa86  newarr   [mscorlib]System.Int32
0xfa8b  stloc.2
0xfa8c  ldarg.0
0xfa8d  ldfld    class System.Deployment.Internal.Isolation.Store System.Deployment.Application.ComponentStore::_store
0xfa92  ldloc.0
0xfa93  ldloc.1
0xfa94  ldloc.2
0xfa95  callvirt instance void System.Deployment.Internal.Isolation.Store::Transact(valuetype System.Deployment.Internal.Isolation.StoreTransactionOperation[] operations, unsigned int32[] rgDispositions, int32[] rgResults)
0xfa9a  ldarg.0
0xfa9b  ldfld    class System.Deployment.Internal.Isolation.IStateManager System.Deployment.Application.ComponentStore::_stateMgr
0xfaa0  ldc.i4.0
0xfaa1  ldloca.s 3
0xfaa3  callvirt instance void System.Deployment.Internal.Isolation.IStateManager::Scavenge([in] unsigned int32 Flags, [out] unsigned int32& Disposition)
0xfaa8  leave.s  loc_FB17
0xfaaa  stloc.s  4
0xfaac  ldc.i4.2
0xfaad  ldstr    aExTransactdire// "Ex_TransactDirectoryNotFoundException"
0xfab2  call     string System.Deployment.Application.Resources::GetString(string s)
0xfab7  ldloc.s  4
0xfab9  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xfabe  throw
0xfabf  stloc.s  5
0xfac1  ldc.i4.2
0xfac2  ldstr    aExStoreoperati// "Ex_StoreOperationFailed"
0xfac7  call     string System.Deployment.Application.Resources::GetString(string s)
0xfacc  ldloc.s  5
0xface  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xfad3  throw
0xfad4  stloc.s  6
0xfad6  ldc.i4.2
0xfad7  ldstr    aExStoreoperati// "Ex_StoreOperationFailed"
0xfadc  call     string System.Deployment.Application.Resources::GetString(string s)
0xfae1  ldloc.s  6
0xfae3  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xfae8  throw
0xfae9  stloc.s  7
0xfaeb  ldc.i4.2
0xfaec  ldstr    aExStoreoperati// "Ex_StoreOperationFailed"
0xfaf1  call     string System.Deployment.Application.Resources::GetString(string s)
0xfaf6  ldloc.s  7
0xfaf8  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0xfafd  throw
0xfafe  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0xfb03  ldc.i4   0x1F91
0xfb08  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0xfb0d  pop
0xfb0e  ldloc.0
0xfb0f  ldloc.1
0xfb10  ldloc.2
0xfb11  call     void System.Deployment.Application.Logger::AddTransactionInformation(valuetype System.Deployment.Internal.Isolation.StoreTransactionOperation[] storeOperations, unsigned int32[] rgDispositions, int32[] rgResults)
0xfb16  endfinally
0xfb17  ldarg.2
0xfb18  brfalse.s loc_FB20
0xfb1a  ldarg.2
0xfb1b  callvirt instance void System.Deployment.Application.SubscriptionState::Invalidate()
0xfb20  ret
```
