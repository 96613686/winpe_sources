# [thunk]:ATL::CComObject<CCommandHandler>::AddRef`adjustor{16}' (void)

- ea: `0x18000a820`
- end: `0x18000a829`
- name: `?AddRef@?$CComObject@VCCommandHandler@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CCommandHandler>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x18000a820  sub     rcx, 10h
0x18000a824  jmp     ?AddRef@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CCommandHandler>::AddRef(void)
```
