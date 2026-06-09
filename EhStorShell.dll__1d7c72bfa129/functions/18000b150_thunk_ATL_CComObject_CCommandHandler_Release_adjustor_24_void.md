# [thunk]:ATL::CComObject<CCommandHandler>::Release`adjustor{24}' (void)

- ea: `0x18000b150`
- end: `0x18000b159`
- name: `?Release@?$CComObject@VCCommandHandler@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b0c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CCommandHandler>::Release((_DWORD *)(a1 - 24));
}

```

## disassembly

```asm
0x18000b150  sub     rcx, 18h
0x18000b154  jmp     ?Release@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CCommandHandler>::Release(void)
```
