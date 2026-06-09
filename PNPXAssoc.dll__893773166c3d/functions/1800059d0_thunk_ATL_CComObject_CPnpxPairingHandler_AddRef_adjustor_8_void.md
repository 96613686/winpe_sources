# [thunk]:ATL::CComObject<CPnpxPairingHandler>::AddRef`adjustor{8}' (void)

- ea: `0x1800059d0`
- end: `0x1800059d9`
- name: `?AddRef@?$CComObject@VCPnpxPairingHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800059a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  return ATL::CComObject<CPnpxPairingHandler>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800059d0  sub     rcx, 8
0x1800059d4  jmp     ?AddRef@?$CComObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CPnpxPairingHandler>::AddRef(void)
```
