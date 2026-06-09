# [thunk]:ATL::CComObject<CWfHelperClass>::Release`adjustor{56}' (void)

- ea: `0x1800058d0`
- end: `0x1800058d9`
- name: `?Release@?$CComObject@VCWfHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005820`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWfHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CWfHelperClass>::Release((volatile signed __int32 *)(a1 - 56));
}

```

## disassembly

```asm
0x1800058d0  sub     rcx, 38h ; '8'
0x1800058d4  jmp     ?Release@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWfHelperClass>::Release(void)
```
