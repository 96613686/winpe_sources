# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x180011900`
- end: `0x180011909`
- name: `?QueryInterface@?$CComContainedObject@VCMigrationPlugin@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800118b0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CMigrationPlugin>::QueryInterface(a1 - 24);
}

```

## disassembly

```asm
0x180011900  sub     rcx, 18h
0x180011904  jmp     ?QueryInterface@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CMigrationPlugin>::QueryInterface(_GUID const &,void * *)
```
