# ATL::CComObject<CMidi2UMP2BSTransform>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006680`
- end: `0x180006692`
- name: `?QueryInterface@?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMidi2UMP2BSTransform>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMidi2UMP2BSTransform::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180006680  mov     r9, r8; void **
0x180006683  mov     r8, rdx; struct _GUID *
0x180006686  lea     rdx, ?_entries@?1??_GetEntries@CMidi2UMP2BSTransform@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000668d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
