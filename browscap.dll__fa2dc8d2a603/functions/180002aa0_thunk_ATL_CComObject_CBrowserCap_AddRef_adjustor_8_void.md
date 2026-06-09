# [thunk]:ATL::CComObject<CBrowserCap>::AddRef`adjustor{8}' (void)

- ea: `0x180002aa0`
- end: `0x180002aa9`
- name: `?AddRef@?$CComObject@VCBrowserCap@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002a70`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::AddRef(__int64 a1)
{
  return ATL::CComObject<CBrowserCap>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002aa0  sub     rcx, 8
0x180002aa4  jmp     ?AddRef@?$CComObject@VCBrowserCap@@@ATL@@UEAAKXZ; ATL::CComObject<CBrowserCap>::AddRef(void)
```
