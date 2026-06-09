# [thunk]:ATL::CComObject<CCompatContextMenu>::AddRef`adjustor{16}' (void)

- ea: `0x180008e30`
- end: `0x180008e39`
- name: `?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CCompatContextMenu>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180008e30  sub     rcx, 10h
0x180008e34  jmp     ?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ; ATL::CComObject<CCompatContextMenu>::AddRef(void)
```
