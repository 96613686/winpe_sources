# [thunk]:CRegistryChangeListener::AddRef`adjustor{8}' (void)

- ea: `0x180009170`
- end: `0x180009179`
- name: `?AddRef@CRegistryChangeListener@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009150`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::AddRef(__int64 a1)
{
  return CRegistryChangeListener::AddRef((CRegistryChangeListener *)(a1 - 8));
}

```

## disassembly

```asm
0x180009170  sub     rcx, 8; this
0x180009174  jmp     ?AddRef@CRegistryChangeListener@@UEAAKXZ; CRegistryChangeListener::AddRef(void)
```
