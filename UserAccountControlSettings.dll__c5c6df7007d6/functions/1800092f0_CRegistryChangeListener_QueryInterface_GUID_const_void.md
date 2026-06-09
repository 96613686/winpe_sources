# CRegistryChangeListener::QueryInterface(_GUID const &,void * *)

- ea: `0x1800092f0`
- end: `0x180009304`
- name: `?QueryInterface@CRegistryChangeListener@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `20`
- prototype: `HRESULT __fastcall(CRegistryChangeListener *this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180009310`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x1800092fd`

## pseudocode

```c
HRESULT __fastcall CRegistryChangeListener::QueryInterface(
        CRegistryChangeListener *this,
        const struct _GUID *a2,
        void **a3)
{
  return QISearch(this, &`CRegistryChangeListener::QueryInterface'::`2'::qit, a2, a3);
}

```

## disassembly

```asm
0x1800092f0  mov     r9, r8
0x1800092f3  mov     r8, rdx
0x1800092f6  lea     rdx, ?qit@?1??QueryInterface@CRegistryChangeListener@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; QITAB const near * const `CRegistryChangeListener::QueryInterface(_GUID const &,void * *)'::`2'::qit
0x1800092fd  jmp     cs:__imp_QISearch
```
