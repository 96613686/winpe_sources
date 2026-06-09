# [thunk]:ATL::CComObject<CSMBHelperClass>::AddRef`adjustor{56}' (void)

- ea: `0x180003e60`
- end: `0x180003e69`
- name: `?AddRef@?$CComObject@VCSMBHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003e20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSMBHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CSMBHelperClass>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x180003e60  sub     rcx, 38h ; '8'
0x180003e64  jmp     ?AddRef@?$CComObject@VCSMBHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CSMBHelperClass>::AddRef(void)
```
