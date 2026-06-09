# [thunk]:ATL::CComContainedObject<CVsShellExtHandler>::Release`adjustor{8}' (void)

- ea: `0x180003490`
- end: `0x180003499`
- name: `?Release@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003290`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180003490  sub     rcx, 8
0x180003494  jmp     ?Release@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CVsShellExtHandler>::Release(void)
```
