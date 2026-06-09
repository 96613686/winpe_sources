# [thunk]:ATL::CComContainedObject<CVsShellExtHandler>::Release`adjustor{16}' (void)

- ea: `0x1800034e0`
- end: `0x1800034e9`
- name: `?Release@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003290`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::Release(a1 - 16);
}

```

## disassembly

```asm
0x1800034e0  sub     rcx, 10h
0x1800034e4  jmp     ?Release@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CVsShellExtHandler>::Release(void)
```
