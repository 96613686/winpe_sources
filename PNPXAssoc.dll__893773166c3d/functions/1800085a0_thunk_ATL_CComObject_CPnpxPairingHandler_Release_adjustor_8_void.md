# [thunk]:ATL::CComObject<CPnpxPairingHandler>::Release`adjustor{8}' (void)

- ea: `0x1800085a0`
- end: `0x1800085a9`
- name: `?Release@?$CComObject@VCPnpxPairingHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008510`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CPnpxPairingHandler>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x1800085a0  sub     rcx, 8
0x1800085a4  jmp     ?Release@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CPnpxPairingHandler>::Release(void)
```
