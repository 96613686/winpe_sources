# ATL::CComObject<CBrowserCap>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004d90`
- end: `0x180004da2`
- name: `?QueryInterface@?$CComObject@VCBrowserCap@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x1800044a8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CBrowserCap::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004d90  mov     r9, r8; void **
0x180004d93  mov     r8, rdx; struct _GUID *
0x180004d96  lea     rdx, ?_entries@?1??_GetEntries@CBrowserCap@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004d9d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
