# [thunk]:ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009330`
- end: `0x180009339`
- name: `?QueryInterface@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009310`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180009330  sub     rcx, 8
0x180009334  jmp     ?QueryInterface@?$CComContainedObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CRemoveDeviceContextHandler>::QueryInterface(_GUID const &,void * *)
```
