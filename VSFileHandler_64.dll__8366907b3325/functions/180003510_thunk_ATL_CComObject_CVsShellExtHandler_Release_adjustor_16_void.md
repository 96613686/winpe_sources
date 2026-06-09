# [thunk]:ATL::CComObject<CVsShellExtHandler>::Release`adjustor{16}' (void)

- ea: `0x180003510`
- end: `0x180003519`
- name: `?Release@?$CComObject@VCVsShellExtHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003210`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CVsShellExtHandler>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x180003510  sub     rcx, 10h
0x180003514  jmp     ?Release@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CVsShellExtHandler>::Release(void)
```
