# [thunk]:CRegistryChangeListener::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009310`
- end: `0x180009319`
- name: `?QueryInterface@CRegistryChangeListener@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `HRESULT __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800092f0`

## pseudocode

```c
HRESULT __fastcall CRegistryChangeListener::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CRegistryChangeListener::QueryInterface((CRegistryChangeListener *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180009310  sub     rcx, 8; this
0x180009314  jmp     ?QueryInterface@CRegistryChangeListener@@UEAAJAEBU_GUID@@PEAPEAX@Z; CRegistryChangeListener::QueryInterface(_GUID const &,void * *)
```
