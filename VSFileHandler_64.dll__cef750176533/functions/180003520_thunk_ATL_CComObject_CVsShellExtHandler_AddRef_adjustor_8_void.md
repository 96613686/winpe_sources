# [thunk]:ATL::CComObject<CVsShellExtHandler>::AddRef`adjustor{8}' (void)

- ea: `0x180003520`
- end: `0x180003529`
- name: `?AddRef@?$CComObject@VCVsShellExtHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003270`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CVsShellExtHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180003520  sub     rcx, 8
0x180003524  jmp     ?AddRef@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CVsShellExtHandler>::AddRef(void)
```
