# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::Release`adjustor{16}' (void)

- ea: `0x180011ef0`
- end: `0x180011ef9`
- name: `?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CMigrationPlugin>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180011ef0  sub     rcx, 10h
0x180011ef4  jmp     ?Release@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMigrationPlugin>::Release(void)
```
