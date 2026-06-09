# ATL::CComObject<TransportManager>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004700`
- end: `0x180004712`
- name: `?QueryInterface@?$CComObject@VTransportManager@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004720`
- `0x180004730`

## callees

- `0x1800043b8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`TransportManager::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004700  mov     r9, r8; void **
0x180004703  mov     r8, rdx; struct _GUID *
0x180004706  lea     rdx, ?_entries@?1??_GetEntries@TransportManager@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000470d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
