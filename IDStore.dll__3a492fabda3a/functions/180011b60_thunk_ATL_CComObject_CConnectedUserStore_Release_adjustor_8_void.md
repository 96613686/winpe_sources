# [thunk]:ATL::CComObject<CConnectedUserStore>::Release`adjustor{8}' (void)

- ea: `0x180011b60`
- end: `0x180011b69`
- name: `?Release@?$CComObject@VCConnectedUserStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d570`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CConnectedUserStore>::Release(__int64 a1)
{
  return ATL::CComObject<CConnectedUserStore>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180011b60  sub     rcx, 8
0x180011b64  jmp     ?Release@?$CComObject@VCConnectedUserStore@@@ATL@@UEAAKXZ; ATL::CComObject<CConnectedUserStore>::Release(void)
```
