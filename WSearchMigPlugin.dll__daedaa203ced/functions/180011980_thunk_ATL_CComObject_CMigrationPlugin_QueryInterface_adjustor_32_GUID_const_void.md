# [thunk]:ATL::CComObject<CMigrationPlugin>::QueryInterface`adjustor{32}' (_GUID const &,void * *)

- ea: `0x180011980`
- end: `0x180011989`
- name: `?QueryInterface@?$CComObject@VCMigrationPlugin@@@ATL@@WCA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011930`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMigrationPlugin>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CMigrationPlugin>::QueryInterface((char *)(a1 - 32), a2, a3);
}

```

## disassembly

```asm
0x180011980  sub     rcx, 20h ; ' '
0x180011984  jmp     ?QueryInterface@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)
```
