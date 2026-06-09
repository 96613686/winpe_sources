# [thunk]:CRuntimeBrokerLifetimeExtensionFactory::AddRef`adjustor{8}' (void)

- ea: `0x14000aee0`
- end: `0x14000aee9`
- name: `?AddRef@CRuntimeBrokerLifetimeExtensionFactory@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007700`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::AddRef(__int64 a1)
{
  return CRuntimeBrokerLifetimeExtensionFactory::AddRef((CRuntimeBrokerLifetimeExtensionFactory *)(a1 - 8));
}

```

## disassembly

```asm
0x14000aee0  sub     rcx, 8; this
0x14000aee4  jmp     ?AddRef@CRuntimeBrokerLifetimeExtensionFactory@@UEAAKXZ; CRuntimeBrokerLifetimeExtensionFactory::AddRef(void)
```
