# [thunk]:CRegistryChangeListener::Release`adjustor{8}' (void)

- ea: `0x180009360`
- end: `0x180009369`
- name: `?Release@CRegistryChangeListener@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009320`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::Release(__int64 a1)
{
  return CRegistryChangeListener::Release((CRegistryChangeListener *)(a1 - 8));
}

```

## disassembly

```asm
0x180009360  sub     rcx, 8; this
0x180009364  jmp     ?Release@CRegistryChangeListener@@UEAAKXZ; CRegistryChangeListener::Release(void)
```
