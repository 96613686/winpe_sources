# [thunk]:ATL::CComContainedObject<CPnpxPairingHandler>::Release`adjustor{16}' (void)

- ea: `0x1800084b0`
- end: `0x1800084b9`
- name: `?Release@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008480`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CPnpxPairingHandler>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CPnpxPairingHandler>::Release(a1 - 16);
}

```

## disassembly

```asm
0x1800084b0  sub     rcx, 10h
0x1800084b4  jmp     ?Release@?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CPnpxPairingHandler>::Release(void)
```
