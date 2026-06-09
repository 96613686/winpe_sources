# [thunk]:ATL::CComObject<TransportManager>::Release`adjustor{16}' (void)

- ea: `0x180004870`
- end: `0x180004879`
- name: `?Release@?$CComObject@VTransportManager@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800047d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TransportManager>::Release(__int64 a1)
{
  return ATL::CComObject<TransportManager>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x180004870  sub     rcx, 10h
0x180004874  jmp     ?Release@?$CComObject@VTransportManager@@@ATL@@UEAAKXZ; ATL::CComObject<TransportManager>::Release(void)
```
