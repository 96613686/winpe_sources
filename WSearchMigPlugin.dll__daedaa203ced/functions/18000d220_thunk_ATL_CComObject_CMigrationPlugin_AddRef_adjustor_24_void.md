# [thunk]:ATL::CComObject<CMigrationPlugin>::AddRef`adjustor{24}' (void)

- ea: `0x18000d220`
- end: `0x18000d229`
- name: `?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CMigrationPlugin>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x18000d220  sub     rcx, 18h
0x18000d224  jmp     ?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComObject<CMigrationPlugin>::AddRef(void)
```
