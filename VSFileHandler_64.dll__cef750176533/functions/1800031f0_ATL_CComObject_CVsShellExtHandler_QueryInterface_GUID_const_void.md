# ATL::CComObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800031f0`
- end: `0x180003202`
- name: `?QueryInterface@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800034b0`
- `0x1800034f0`

## callees

- `0x18000372c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CVsShellExtHandler::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800031f0  mov     r9, r8; void **
0x1800031f3  mov     r8, rdx; struct _GUID *
0x1800031f6  lea     rdx, ?_entries@?1??_GetEntries@CVsShellExtHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800031fd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
