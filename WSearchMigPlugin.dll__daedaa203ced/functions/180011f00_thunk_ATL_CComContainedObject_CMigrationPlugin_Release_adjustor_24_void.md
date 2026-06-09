# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::Release`adjustor{24}' (void)

- ea: `0x180011f00`
- end: `0x180011f09`
- name: `?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011eb0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CMigrationPlugin>::Release(a1 - 24);
}

```

## disassembly

```asm
0x180011f00  sub     rcx, 18h
0x180011f04  jmp     ?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMigrationPlugin>::Release(void)
```
