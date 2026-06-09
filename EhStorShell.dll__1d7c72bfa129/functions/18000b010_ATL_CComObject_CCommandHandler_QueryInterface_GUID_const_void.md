# ATL::CComObject<CCommandHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000b010`
- end: `0x18000b022`
- name: `?QueryInterface@?$CComObject@VCCommandHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b030`
- `0x18000b040`
- `0x18000b050`

## callees

- `0x1800015c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CCommandHandler::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000b010  mov     r9, r8; void **
0x18000b013  mov     r8, rdx; struct _GUID *
0x18000b016  lea     rdx, ?_entries@?1??_GetEntries@CCommandHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000b01d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
