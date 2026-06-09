# ATL::CComObject<sandbox::SandboxFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x140006150`
- end: `0x140006162`
- name: `?QueryInterface@?$CComObject@VSandboxFactory@sandbox@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<sandbox::SandboxFactory>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`sandbox::SandboxFactory::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x140006150  mov     r9, r8; void **
0x140006153  mov     r8, rdx; struct _GUID *
0x140006156  lea     rdx, ?_entries@?1??_GetEntries@SandboxFactory@sandbox@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU45@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000615d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
