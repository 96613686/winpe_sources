# [thunk]:ATL::CComObjectCached<CRemoteAssistance>::AddRef`adjustor{8}' (void)

- ea: `0x140004610`
- end: `0x140004619`
- name: `?AddRef@?$CComObjectCached@VCRemoteAssistance@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400045d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CRemoteAssistance>::AddRef(__int64 a1)
{
  return ATL::CComObjectCached<CRemoteAssistance>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x140004610  sub     rcx, 8
0x140004614  jmp     ?AddRef@?$CComObjectCached@VCRemoteAssistance@@@ATL@@UEAAKXZ; ATL::CComObjectCached<CRemoteAssistance>::AddRef(void)
```
