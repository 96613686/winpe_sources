# [thunk]:ATL::CComObject<CWfHelperClass>::Release`adjustor{8}' (void)

- ea: `0x1800058c0`
- end: `0x1800058c9`
- name: `?Release@?$CComObject@VCWfHelperClass@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CWfHelperClass>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x1800058c0  sub     rcx, 8
0x1800058c4  jmp     ?Release@?$CComObject@VCWfHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWfHelperClass>::Release(void)
```
