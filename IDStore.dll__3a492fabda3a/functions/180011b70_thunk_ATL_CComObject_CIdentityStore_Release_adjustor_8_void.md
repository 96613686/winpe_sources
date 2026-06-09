# [thunk]:ATL::CComObject<CIdentityStore>::Release`adjustor{8}' (void)

- ea: `0x180011b70`
- end: `0x180011b79`
- name: `?Release@?$CComObject@VCIdentityStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c570`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::Release(__int64 a1)
{
  return ATL::CComObject<CIdentityStore>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180011b70  sub     rcx, 8
0x180011b74  jmp     ?Release@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComObject<CIdentityStore>::Release(void)
```
