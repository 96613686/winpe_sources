# [thunk]:ATL::CComObject<CMigrationPlugin>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x180011970`
- end: `0x180011979`
- name: `?QueryInterface@?$CComObject@VCMigrationPlugin@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CMigrationPlugin>::QueryInterface((char *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x180011970  sub     rcx, 18h
0x180011974  jmp     ?QueryInterface@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)
```
