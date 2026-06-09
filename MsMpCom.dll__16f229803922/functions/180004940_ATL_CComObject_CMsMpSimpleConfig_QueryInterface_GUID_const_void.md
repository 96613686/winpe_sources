# ATL::CComObject<CMsMpSimpleConfig>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004940`
- end: `0x180004956`
- name: `?QueryInterface@?$CComObject@VCMsMpSimpleConfig@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000420c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsMpSimpleConfig>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           (char *)(a1 - 64),
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMsMpSimpleConfig::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004940  mov     r9, r8; void **
0x180004943  add     rcx, 0FFFFFFFFFFFFFFC0h; void *
0x180004947  mov     r8, rdx; struct _GUID *
0x18000494a  lea     rdx, ?_entries@?1??_GetEntries@CMsMpSimpleConfig@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004951  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
