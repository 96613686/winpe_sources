# ATL::CComObject<CDfsShellAdmin>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005250`
- end: `0x180005262`
- name: `?QueryInterface@?$CComObject@VCDfsShellAdmin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004b24`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDfsShellAdmin>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CDfsShellAdmin::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180005250  mov     r9, r8; void **
0x180005253  mov     r8, rdx; struct _GUID *
0x180005256  lea     rdx, ?_entries@?1??_GetEntries@CDfsShellAdmin@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000525d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
