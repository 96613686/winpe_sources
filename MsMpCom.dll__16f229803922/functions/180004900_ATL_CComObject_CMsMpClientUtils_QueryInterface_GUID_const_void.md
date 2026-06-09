# ATL::CComObject<CMsMpClientUtils>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004900`
- end: `0x180004916`
- name: `?QueryInterface@?$CComObject@VCMsMpClientUtils@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000420c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsMpClientUtils>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           (char *)(a1 - 64),
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMsMpClientUtils::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004900  mov     r9, r8; void **
0x180004903  add     rcx, 0FFFFFFFFFFFFFFC0h; void *
0x180004907  mov     r8, rdx; struct _GUID *
0x18000490a  lea     rdx, ?_entries@?1??_GetEntries@CMsMpClientUtils@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004911  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
