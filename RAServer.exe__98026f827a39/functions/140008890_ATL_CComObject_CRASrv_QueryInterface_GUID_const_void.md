# ATL::CComObject<CRASrv>::QueryInterface(_GUID const &,void * *)

- ea: `0x140008890`
- end: `0x1400088a2`
- name: `?QueryInterface@?$CComObject@VCRASrv@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400088b0`

## callees

- `0x140004db8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRASrv>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRASrv::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x140008890  mov     r9, r8; void **
0x140008893  mov     r8, rdx; struct _GUID *
0x140008896  lea     rdx, ?_entries@?1??_GetEntries@CRASrv@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000889d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
