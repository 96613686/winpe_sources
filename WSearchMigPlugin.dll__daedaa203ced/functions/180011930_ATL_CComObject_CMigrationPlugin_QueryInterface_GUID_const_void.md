# ATL::CComObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011930`
- end: `0x180011942`
- name: `?QueryInterface@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011950`
- `0x180011960`
- `0x180011970`
- `0x180011980`
- `0x180011990`

## callees

- `0x18001013c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMigrationPlugin>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMigrationPlugin::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180011930  mov     r9, r8; void **
0x180011933  mov     r8, rdx; struct _GUID *
0x180011936  lea     rdx, ?_entries@?1??_GetEntries@CMigrationPlugin@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18001193d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
