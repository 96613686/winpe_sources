# ATL::CComObjectCached<CRemoteAssistance>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400088c0`
- end: `0x1400088d2`
- name: `?QueryInterface@?$CComObjectCached@VCRemoteAssistance@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400088e0`

## callees

- `0x140004db8`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CRemoteAssistance>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRemoteAssistance::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1400088c0  mov     r9, r8; void **
0x1400088c3  mov     r8, rdx; struct _GUID *
0x1400088c6  lea     rdx, ?_entries@?1??_GetEntries@CRemoteAssistance@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1400088cd  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
