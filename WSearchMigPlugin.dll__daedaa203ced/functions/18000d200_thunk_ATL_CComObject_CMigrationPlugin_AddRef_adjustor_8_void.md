# [thunk]:ATL::CComObject<CMigrationPlugin>::AddRef`adjustor{8}' (void)

- ea: `0x18000d200`
- end: `0x18000d209`
- name: `?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d1d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMigrationPlugin>::AddRef(__int64 a1)
{
  return ATL::CComObject<CMigrationPlugin>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000d200  sub     rcx, 8
0x18000d204  jmp     ?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComObject<CMigrationPlugin>::AddRef(void)
```
