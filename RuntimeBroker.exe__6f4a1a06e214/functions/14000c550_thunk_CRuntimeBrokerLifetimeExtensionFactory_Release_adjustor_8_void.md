# [thunk]:CRuntimeBrokerLifetimeExtensionFactory::Release`adjustor{8}' (void)

- ea: `0x14000c550`
- end: `0x14000c559`
- name: `?Release@CRuntimeBrokerLifetimeExtensionFactory@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400068a0`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::Release(__int64 a1)
{
  return CRuntimeBrokerLifetimeExtensionFactory::Release((CRuntimeBrokerLifetimeExtensionFactory *)(a1 - 8));
}

```

## disassembly

```asm
0x14000c550  sub     rcx, 8; this
0x14000c554  jmp     ?Release@CRuntimeBrokerLifetimeExtensionFactory@@UEAAKXZ; CRuntimeBrokerLifetimeExtensionFactory::Release(void)
```
