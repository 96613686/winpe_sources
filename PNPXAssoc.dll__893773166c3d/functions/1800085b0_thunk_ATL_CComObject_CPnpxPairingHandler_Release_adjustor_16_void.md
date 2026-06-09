# [thunk]:ATL::CComObject<CPnpxPairingHandler>::Release`adjustor{16}' (void)

- ea: `0x1800085b0`
- end: `0x1800085b9`
- name: `?Release@?$CComObject@VCPnpxPairingHandler@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CPnpxPairingHandler>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x1800085b0  sub     rcx, 10h
0x1800085b4  jmp     ?Release@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CPnpxPairingHandler>::Release(void)
```
