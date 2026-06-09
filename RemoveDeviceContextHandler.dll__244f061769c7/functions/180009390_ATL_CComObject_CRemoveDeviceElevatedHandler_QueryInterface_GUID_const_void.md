# ATL::CComObject<CRemoveDeviceElevatedHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009390`
- end: `0x1800093a2`
- name: `?QueryInterface@?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008498`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceElevatedHandler>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRemoveDeviceElevatedHandler::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180009390  mov     r9, r8; void **
0x180009393  mov     r8, rdx; struct _GUID *
0x180009396  lea     rdx, ?_entries@?1??_GetEntries@CRemoveDeviceElevatedHandler@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000939d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
