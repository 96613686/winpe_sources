# [thunk]:ATL::CComObject<CVsShellExtHandler>::AddRef`adjustor{16}' (void)

- ea: `0x180003480`
- end: `0x180003489`
- name: `?AddRef@?$CComObject@VCVsShellExtHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003270`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CVsShellExtHandler>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180003480  sub     rcx, 10h
0x180003484  jmp     ?AddRef@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CVsShellExtHandler>::AddRef(void)
```
