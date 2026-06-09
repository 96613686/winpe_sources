# [thunk]:ATL::CComObject<CIdentityStore>::AddRef`adjustor{8}' (void)

- ea: `0x180010c90`
- end: `0x180010c99`
- name: `?AddRef@?$CComObject@VCIdentityStore@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CIdentityStore>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180010c90  sub     rcx, 8
0x180010c94  jmp     ?AddRef@?$CComObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComObject<CIdentityStore>::AddRef(void)
```
