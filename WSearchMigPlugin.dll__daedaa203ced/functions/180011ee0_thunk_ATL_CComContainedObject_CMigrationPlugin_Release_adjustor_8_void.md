# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::Release`adjustor{8}' (void)

- ea: `0x180011ee0`
- end: `0x180011ee9`
- name: `?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@W7EAAKXZ`
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
  return ATL::CComContainedObject<CMigrationPlugin>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180011ee0  sub     rcx, 8
0x180011ee4  jmp     ?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMigrationPlugin>::Release(void)
```
