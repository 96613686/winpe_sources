# ATL::CComObject<CMidi2SchedulerTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006790`
- end: `0x1800067a2`
- name: `?QueryInterface@?$CComObject@VCMidi2SchedulerTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005d30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2SchedulerTransform>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2SchedulerTransform::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180006790  mov     r9, r8; void **
0x180006793  mov     r8, rdx; struct _GUID *
0x180006796  lea     rdx, ?_entries@?1??_GetEntries@CMidi2SchedulerTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000679d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
