# [thunk]:ATL::CComContainedObject<CConnectedUserStore>::AddRef`adjustor{8}' (void)

- ea: `0x180010c10`
- end: `0x180010c19`
- name: `?AddRef@?$CComContainedObject@VCConnectedUserStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010bf0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CConnectedUserStore>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180010c10  sub     rcx, 8
0x180010c14  jmp     ?AddRef@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CConnectedUserStore>::AddRef(void)
```
