# [thunk]:ATL::CComContainedObject<CIdentityStore>::Release`adjustor{16}' (void)

- ea: `0x180011b50`
- end: `0x180011b59`
- name: `?Release@?$CComContainedObject@VCIdentityStore@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011b20`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CIdentityStore>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CIdentityStore>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180011b50  sub     rcx, 10h
0x180011b54  jmp     ?Release@?$CComContainedObject@VCIdentityStore@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CIdentityStore>::Release(void)
```
