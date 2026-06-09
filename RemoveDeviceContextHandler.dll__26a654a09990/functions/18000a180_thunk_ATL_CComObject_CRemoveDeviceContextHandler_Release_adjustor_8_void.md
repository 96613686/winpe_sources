# [thunk]:ATL::CComObject<CRemoveDeviceContextHandler>::Release`adjustor{8}' (void)

- ea: `0x18000a180`
- end: `0x18000a189`
- name: `?Release@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a100`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceContextHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CRemoveDeviceContextHandler>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000a180  sub     rcx, 8
0x18000a184  jmp     ?Release@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CRemoveDeviceContextHandler>::Release(void)
```
