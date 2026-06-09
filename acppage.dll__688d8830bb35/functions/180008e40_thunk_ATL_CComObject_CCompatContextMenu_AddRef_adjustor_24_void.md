# [thunk]:ATL::CComObject<CCompatContextMenu>::AddRef`adjustor{24}' (void)

- ea: `0x180008e40`
- end: `0x180008e49`
- name: `?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CCompatContextMenu>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180008e40  sub     rcx, 18h
0x180008e44  jmp     ?AddRef@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ; ATL::CComObject<CCompatContextMenu>::AddRef(void)
```
