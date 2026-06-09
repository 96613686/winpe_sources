# [thunk]:ATL::CComContainedObject<CConnectedUserStore>::Release`adjustor{8}' (void)

- ea: `0x180011af0`
- end: `0x180011af9`
- name: `?Release@?$CComContainedObject@VCConnectedUserStore@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011ad0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CConnectedUserStore>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CConnectedUserStore>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180011af0  sub     rcx, 8
0x180011af4  jmp     ?Release@?$CComContainedObject@VCConnectedUserStore@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CConnectedUserStore>::Release(void)
```
