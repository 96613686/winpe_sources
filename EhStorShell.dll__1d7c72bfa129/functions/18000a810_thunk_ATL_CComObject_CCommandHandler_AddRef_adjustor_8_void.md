# [thunk]:ATL::CComObject<CCommandHandler>::AddRef`adjustor{8}' (void)

- ea: `0x18000a810`
- end: `0x18000a819`
- name: `?AddRef@?$CComObject@VCCommandHandler@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CCommandHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x18000a810  sub     rcx, 8
0x18000a814  jmp     ?AddRef@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CCommandHandler>::AddRef(void)
```
