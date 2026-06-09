# [thunk]:ATL::CComObject<CRemoveDeviceContextHandler>::AddRef`adjustor{8}' (void)

- ea: `0x1800066e0`
- end: `0x1800066e9`
- name: `?AddRef@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800066c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceContextHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CRemoveDeviceContextHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800066e0  sub     rcx, 8
0x1800066e4  jmp     ?AddRef@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CRemoveDeviceContextHandler>::AddRef(void)
```
