# [thunk]:ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef`adjustor{8}' (void)

- ea: `0x180006690`
- end: `0x180006699`
- name: `?AddRef@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006670`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180006690  sub     rcx, 8
0x180006694  jmp     ?AddRef@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRemoveDeviceContextHandler>::AddRef(void)
```
