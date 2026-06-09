# [thunk]:ATL::CComObject<CIdentityStore>::Release`adjustor{16}' (void)

- ea: `0x180011b80`
- end: `0x180011b89`
- name: `?Release@?$CComObject@VCIdentityStore@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CIdentityStore>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x180011b80  sub     rcx, 10h
0x180011b84  jmp     ?Release@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComObject<CIdentityStore>::Release(void)
```
