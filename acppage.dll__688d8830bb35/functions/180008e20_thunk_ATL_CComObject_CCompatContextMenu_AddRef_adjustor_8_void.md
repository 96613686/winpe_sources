# [thunk]:ATL::CComObject<CCompatContextMenu>::AddRef`adjustor{8}' (void)

- ea: `0x180008e20`
- end: `0x180008e29`
- name: `?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008df0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCompatContextMenu>::AddRef(__int64 a1)
{
  return ATL::CComObject<CCompatContextMenu>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180008e20  sub     rcx, 8
0x180008e24  jmp     ?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ; ATL::CComObject<CCompatContextMenu>::AddRef(void)
```
