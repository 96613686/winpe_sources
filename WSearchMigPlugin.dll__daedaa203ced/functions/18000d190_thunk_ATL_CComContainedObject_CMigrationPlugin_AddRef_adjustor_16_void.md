# [thunk]:ATL::CComContainedObject<CMigrationPlugin>::AddRef`adjustor{16}' (void)

- ea: `0x18000d190`
- end: `0x18000d199`
- name: `?AddRef@?$CComContainedObject@VCMigrationPlugin@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CMigrationPlugin>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x18000d190  sub     rcx, 10h
0x18000d194  jmp     ?AddRef@?$CComContainedObject@VCMigrationPlugin@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CMigrationPlugin>::AddRef(void)
```
