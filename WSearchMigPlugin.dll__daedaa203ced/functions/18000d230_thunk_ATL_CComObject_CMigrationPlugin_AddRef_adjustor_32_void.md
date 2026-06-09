# [thunk]:ATL::CComObject<CMigrationPlugin>::AddRef`adjustor{32}' (void)

- ea: `0x18000d230`
- end: `0x18000d239`
- name: `?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComObject<CMigrationPlugin>::AddRef(a1 - 32);
}

```

## disassembly

```asm
0x18000d230  sub     rcx, 20h ; ' '
0x18000d234  jmp     ?AddRef@?$CComObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComObject<CMigrationPlugin>::AddRef(void)
```
