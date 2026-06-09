# [thunk]:ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release`adjustor{8}' (void)

- ea: `0x18000a0d0`
- end: `0x18000a0d9`
- name: `?Release@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a0b0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release(a1 - 8);
}

```

## disassembly

```asm
0x18000a0d0  sub     rcx, 8
0x18000a0d4  jmp     ?Release@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRemoveDeviceContextHandler>::Release(void)
```
