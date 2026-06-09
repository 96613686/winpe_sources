# [thunk]:ATL::CComContainedObject<CIdentityStore>::AddRef`adjustor{8}' (void)

- ea: `0x180010c60`
- end: `0x180010c69`
- name: `?AddRef@?$CComContainedObject@VCIdentityStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010c40`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CIdentityStore>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180010c60  sub     rcx, 8
0x180010c64  jmp     ?AddRef@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CIdentityStore>::AddRef(void)
```
