# [thunk]:ATL::CComObject<CCommandHandler>::AddRef`adjustor{24}' (void)

- ea: `0x18000a830`
- end: `0x18000a839`
- name: `?AddRef@?$CComObject@VCCommandHandler@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a800`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CCommandHandler>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x18000a830  sub     rcx, 18h
0x18000a834  jmp     ?AddRef@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CCommandHandler>::AddRef(void)
```
