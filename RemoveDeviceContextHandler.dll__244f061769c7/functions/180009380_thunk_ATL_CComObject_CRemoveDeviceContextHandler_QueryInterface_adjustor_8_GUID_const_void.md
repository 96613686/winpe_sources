# [thunk]:ATL::CComObject<CRemoveDeviceContextHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009380`
- end: `0x180009389`
- name: `?QueryInterface@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009360`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRemoveDeviceContextHandler>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CRemoveDeviceContextHandler>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180009380  sub     rcx, 8
0x180009384  jmp     ?QueryInterface@?$CComObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CRemoveDeviceContextHandler>::QueryInterface(_GUID const &,void * *)
```
