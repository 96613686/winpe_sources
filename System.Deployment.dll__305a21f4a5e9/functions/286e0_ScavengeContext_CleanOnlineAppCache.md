# ScavengeContext::CleanOnlineAppCache

- ea: `0x286e0`
- end: `0x2878b`
- name: `ScavengeContext::CleanOnlineAppCache`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0xe340`

## callees

- `0xe260`
- `0xf4f0`
- `0xfa50`
- `0xfc00`
- `0x28490`
- `0x286e0`
- `0x287b0`
- `0x28c00`

## pseudocode

```c

```

## disassembly

```asm
0x286e0  ldarg.0
0x286e1  ldloca.s 0
0x286e3  call     instance class SubInstance[] ScavengeContext::CollectOnlineApps([out] class System.Deployment.Internal.Isolation.IDefinitionAppId[]& deployAppIdPtrs)
0x286e8  stloc.1
0x286e9  ldarg.0
0x286ea  ldfld    class System.Deployment.Application.ComponentStore ScavengeContext::_compStore
0x286ef  newobj   instance void StoreTransactionContext::.ctor(class System.Deployment.Application.ComponentStore compStore)
0x286f4  stloc.s  4
0x286f6  ldloc.1
0x286f7  stloc.s  5
0x286f9  ldc.i4.0
0x286fa  stloc.s  6
0x286fc  br.s     loc_28737
0x286fe  ldloc.s  5
0x28700  ldloc.s  6
0x28702  ldelem.ref
0x28703  stloc.s  7
0x28705  ldloc.s  7
0x28707  ldfld    class System.Deployment.Application.SubscriptionState SubInstance::SubState
0x2870c  newobj   instance void System.Deployment.Application.SubscriptionStateInternal::.ctor(class System.Deployment.Application.SubscriptionState subState)
0x28711  stloc.s  8
0x28713  ldloc.s  8
0x28715  ldc.i4.0
0x28716  stfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0x2871b  ldarg.0
0x2871c  ldfld    class System.Deployment.Application.ComponentStore ScavengeContext::_compStore
0x28721  ldloc.s  4
0x28723  ldloc.s  7
0x28725  ldfld    class System.Deployment.Application.SubscriptionState SubInstance::SubState
0x2872a  ldloc.s  8
0x2872c  callvirt instance void System.Deployment.Application.ComponentStore::PrepareFinalizeSubscriptionState(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.SubscriptionStateInternal newState)
0x28731  ldloc.s  6
0x28733  ldc.i4.1
0x28734  add
0x28735  stloc.s  6
0x28737  ldloc.s  6
0x28739  ldloc.s  5
0x2873b  ldlen
0x2873c  conv.i4
0x2873d  blt.s    loc_286FE
0x2873f  ldarg.0
0x28740  ldfld    class System.Deployment.Application.ComponentStore ScavengeContext::_compStore
0x28745  ldloc.s  4
0x28747  ldnull
0x28748  callvirt instance void System.Deployment.Application.ComponentStore::SubmitStoreTransaction(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState)
0x2874d  leave.s  loc_2875B
0x2874f  ldloc.s  4
0x28751  brfalse.s loc_2875A
0x28753  ldloc.s  4
0x28755  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2875a  endfinally
0x2875b  ldarg.0
0x2875c  ldloca.s 0
0x2875e  call     instance class SubInstance[] ScavengeContext::CollectOnlineApps([out] class System.Deployment.Internal.Isolation.IDefinitionAppId[]& deployAppIdPtrs)
0x28763  stloc.1
0x28764  ldc.i4.0
0x28765  conv.i8
0x28766  stloc.2
0x28767  ldc.i4.0
0x28768  conv.i8
0x28769  stloc.3
0x2876a  ldloc.0
0x2876b  ldlen
0x2876c  brfalse.s loc_28784
0x2876e  ldarg.0
0x2876f  ldfld    class System.Deployment.Application.ComponentStore ScavengeContext::_compStore
0x28774  ldloc.0
0x28775  ldlen
0x28776  conv.i4
0x28777  ldloc.0
0x28778  ldc.i4.m1
0x28779  conv.i8
0x2877a  ldloca.s 2
0x2877c  ldloca.s 3
0x2877e  callvirt instance int32 System.Deployment.Application.ComponentStore::CalculateDeploymentsUnderQuota(int32 numberOfDeployments, class System.Deployment.Internal.Isolation.IDefinitionAppId[] deployAppIdPtrs, unsigned int64 quotaSize, unsigned int64& privateSize, unsigned int64& sharedSize)
0x28783  pop
0x28784  ldloc.2
0x28785  call     void ScavengeContext::PersistOnlineAppQuotaUsageEstimate(unsigned int64 usage)
0x2878a  ret
```
