# [thunk]:ATL::CComObject<CSMBHelperClass>::Release`adjustor{56}' (void)

- ea: `0x180008090`
- end: `0x180008099`
- name: `?Release@?$CComObject@VCSMBHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ff0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSMBHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CSMBHelperClass>::Release((volatile signed __int32 *)(a1 - 56));
}

```

## disassembly

```asm
0x180008090  sub     rcx, 38h ; '8'
0x180008094  jmp     ?Release@?$CComObject@VCSMBHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CSMBHelperClass>::Release(void)
```
