# [thunk]:ATL::CComObject<CConnectedUserStore>::AddRef`adjustor{8}' (void)

- ea: `0x180010c80`
- end: `0x180010c89`
- name: `?AddRef@?$CComObject@VCConnectedUserStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e020`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::AddRef(__int64 a1)
{
  return ATL::CComObject<CConnectedUserStore>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180010c80  sub     rcx, 8
0x180010c84  jmp     ?AddRef@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAKXZ; ATL::CComObject<CConnectedUserStore>::AddRef(void)
```
