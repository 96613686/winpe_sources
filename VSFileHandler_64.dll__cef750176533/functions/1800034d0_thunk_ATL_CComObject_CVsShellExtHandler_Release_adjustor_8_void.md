# [thunk]:ATL::CComObject<CVsShellExtHandler>::Release`adjustor{8}' (void)

- ea: `0x1800034d0`
- end: `0x1800034d9`
- name: `?Release@?$CComObject@VCVsShellExtHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003210`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CVsShellExtHandler>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x1800034d0  sub     rcx, 8
0x1800034d4  jmp     ?Release@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CVsShellExtHandler>::Release(void)
```
