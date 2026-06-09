# [thunk]:ATL::CComObject<CWfHelperClass>::AddRef`adjustor{56}' (void)

- ea: `0x180002ba0`
- end: `0x180002ba9`
- name: `?AddRef@?$CComObject@VCWfHelperClass@@@ATL@@WDI@EAAKXZ`
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
  return ATL::CComObject<CWfHelperClass>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x180002ba0  sub     rcx, 38h ; '8'
0x180002ba4  jmp     ?AddRef@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWfHelperClass>::AddRef(void)
```
