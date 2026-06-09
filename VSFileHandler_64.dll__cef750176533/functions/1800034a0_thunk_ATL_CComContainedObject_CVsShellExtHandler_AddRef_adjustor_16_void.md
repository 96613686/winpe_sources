# [thunk]:ATL::CComContainedObject<CVsShellExtHandler>::AddRef`adjustor{16}' (void)

- ea: `0x1800034a0`
- end: `0x1800034a9`
- name: `?AddRef@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CVsShellExtHandler>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x1800034a0  sub     rcx, 10h
0x1800034a4  jmp     ?AddRef@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CVsShellExtHandler>::AddRef(void)
```
