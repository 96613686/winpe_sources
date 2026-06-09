# [thunk]:ATL::CComContainedObject<CVsShellExtHandler>::AddRef`adjustor{8}' (void)

- ea: `0x180003470`
- end: `0x180003479`
- name: `?AddRef@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800032a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180003470  sub     rcx, 8
0x180003474  jmp     ?AddRef@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CVsShellExtHandler>::AddRef(void)
```
