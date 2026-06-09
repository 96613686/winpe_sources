# [thunk]:ATL::CComContainedObject<CBrowserCap>::AddRef`adjustor{8}' (void)

- ea: `0x180002a60`
- end: `0x180002a69`
- name: `?AddRef@?$CComContainedObject@VCBrowserCap@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002a40`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CBrowserCap>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002a60  sub     rcx, 8
0x180002a64  jmp     ?AddRef@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CBrowserCap>::AddRef(void)
```
