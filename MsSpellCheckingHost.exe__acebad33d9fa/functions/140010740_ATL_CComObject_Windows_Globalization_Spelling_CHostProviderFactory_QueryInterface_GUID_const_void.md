# ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x140010740`
- end: `0x140010752`
- name: `?QueryInterface@?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b3c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`Windows::Globalization::Spelling::CHostProviderFactory::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x140010740  mov     r9, r8; void **
0x140010743  mov     r8, rdx; struct _GUID *
0x140010746  lea     rdx, ?_entries@?1??_GetEntries@CHostProviderFactory@Spelling@Globalization@Windows@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU67@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14001074d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
