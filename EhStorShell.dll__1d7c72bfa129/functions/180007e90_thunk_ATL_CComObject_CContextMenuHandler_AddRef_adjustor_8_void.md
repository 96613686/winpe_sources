# [thunk]:ATL::CComObject<CContextMenuHandler>::AddRef`adjustor{8}' (void)

- ea: `0x180007e90`
- end: `0x180007e99`
- name: `?AddRef@?$CComObject@VCContextMenuHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006250`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CContextMenuHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180007e90  sub     rcx, 8
0x180007e94  jmp     ?AddRef@?$CComObject@VCContextMenuHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CContextMenuHandler>::AddRef(void)
```
