# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::AddRef`adjustor{16}' (void)

- ea: `0x180005940`
- end: `0x180005949`
- name: `?AddRef@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005910`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180005940  sub     rcx, 10h
0x180005944  jmp     ?AddRef@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CPnpxPairingHandler>::AddRef(void)
```
