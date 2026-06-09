# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::AddRef`adjustor{32}' (void)

- ea: `0x18000d1b0`
- end: `0x18000d1b9`
- name: `?AddRef@?$CComContainedObject@VCMigrationPlugin@@@ATL@@WCA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d150`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CMigrationPlugin>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CMigrationPlugin>::AddRef(a1 - 32);
}

```

## disassembly

```asm
0x18000d1b0  sub     rcx, 20h ; ' '
0x18000d1b4  jmp     ?AddRef@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMigrationPlugin>::AddRef(void)
```
