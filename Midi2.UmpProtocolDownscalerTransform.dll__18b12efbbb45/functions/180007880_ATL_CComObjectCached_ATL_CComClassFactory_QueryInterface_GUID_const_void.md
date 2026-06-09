# ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007880`
- end: `0x180007892`
- name: `?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006e00`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComClassFactory::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007880  mov     r9, r8; void **
0x180007883  mov     r8, rdx; struct _GUID *
0x180007886  lea     rdx, ?_entries@?1??_GetEntries@CComClassFactory@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000788d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
