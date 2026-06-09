# [thunk]:CRuntimeBrokerLifetimeExtensionFactory::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x14000c170`
- end: `0x14000c179`
- name: `?QueryInterface@CRuntimeBrokerLifetimeExtensionFactory@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140006b30`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        void **a3)
{
  return CRuntimeBrokerLifetimeExtensionFactory::QueryInterface(
           (CRuntimeBrokerLifetimeExtensionFactory *)(a1 - 8),
           a2,
           a3);
}

```

## disassembly

```asm
0x14000c170  sub     rcx, 8; this
0x14000c174  jmp     ?QueryInterface@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CRuntimeBrokerLifetimeExtensionFactory::QueryInterface(_GUID const &,void * *)
```
