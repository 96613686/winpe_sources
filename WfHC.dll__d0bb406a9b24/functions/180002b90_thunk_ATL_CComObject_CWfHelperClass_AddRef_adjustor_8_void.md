# [thunk]:ATL::CComObject<CWfHelperClass>::AddRef`adjustor{8}' (void)

- ea: `0x180002b90`
- end: `0x180002b99`
- name: `?AddRef@?$CComObject@VCWfHelperClass@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWfHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWfHelperClass>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002b90  sub     rcx, 8
0x180002b94  jmp     ?AddRef@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWfHelperClass>::AddRef(void)
```
