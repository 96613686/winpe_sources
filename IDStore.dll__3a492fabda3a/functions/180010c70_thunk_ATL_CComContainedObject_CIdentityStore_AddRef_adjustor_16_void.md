# [thunk]:ATL::CComContainedObject<CIdentityStore>::AddRef`adjustor{16}' (void)

- ea: `0x180010c70`
- end: `0x180010c79`
- name: `?AddRef@?$CComContainedObject@VCIdentityStore@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CIdentityStore>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180010c70  sub     rcx, 10h
0x180010c74  jmp     ?AddRef@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CIdentityStore>::AddRef(void)
```
