# ATL::CComObject<CTieringEngineTaskHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x140003bb0`
- end: `0x140003bc2`
- name: `?QueryInterface@?$CComObject@VCTieringEngineTaskHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400035e4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTieringEngineTaskHandler>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CTieringEngineTaskHandler::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x140003bb0  mov     r9, r8; void **
0x140003bb3  mov     r8, rdx; struct _GUID *
0x140003bb6  lea     rdx, ?_entries@?1??_GetEntries@CTieringEngineTaskHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140003bbd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
