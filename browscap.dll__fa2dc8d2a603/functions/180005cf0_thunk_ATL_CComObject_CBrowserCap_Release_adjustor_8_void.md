# [thunk]:ATL::CComObject<CBrowserCap>::Release`adjustor{8}' (void)

- ea: `0x180005cf0`
- end: `0x180005cf9`
- name: `?Release@?$CComObject@VCBrowserCap@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005c60`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CBrowserCap>::Release(__int64 a1)
{
  return ATL::CComObject<CBrowserCap>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180005cf0  sub     rcx, 8
0x180005cf4  jmp     ?Release@?$CComObject@VCBrowserCap@@@ATL@@UEAAKXZ; ATL::CComObject<CBrowserCap>::Release(void)
```
