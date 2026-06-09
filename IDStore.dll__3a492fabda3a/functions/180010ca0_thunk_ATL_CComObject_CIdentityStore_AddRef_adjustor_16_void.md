# [thunk]:ATL::CComObject<CIdentityStore>::AddRef`adjustor{16}' (void)

- ea: `0x180010ca0`
- end: `0x180010ca9`
- name: `?AddRef@?$CComObject@VCIdentityStore@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000df90`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIdentityStore>::AddRef(__int64 a1)
{
  return ATL::CComObject<CIdentityStore>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180010ca0  sub     rcx, 10h
0x180010ca4  jmp     ?AddRef@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComObject<CIdentityStore>::AddRef(void)
```
