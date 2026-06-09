# [thunk]:ATL::CComObject<TransportManager>::AddRef`adjustor{8}' (void)

- ea: `0x180004170`
- end: `0x180004179`
- name: `?AddRef@?$CComObject@VTransportManager@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004140`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::AddRef(__int64 a1)
{
  return ATL::CComObject<TransportManager>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180004170  sub     rcx, 8
0x180004174  jmp     ?AddRef@?$CComObject@VTransportManager@@@ATL@@UEAAKXZ; ATL::CComObject<TransportManager>::AddRef(void)
```
