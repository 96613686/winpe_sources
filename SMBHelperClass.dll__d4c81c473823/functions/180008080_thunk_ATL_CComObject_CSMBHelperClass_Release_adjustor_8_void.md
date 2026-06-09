# [thunk]:ATL::CComObject<CSMBHelperClass>::Release`adjustor{8}' (void)

- ea: `0x180008080`
- end: `0x180008089`
- name: `?Release@?$CComObject@VCSMBHelperClass@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CSMBHelperClass>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180008080  sub     rcx, 8
0x180008084  jmp     ?Release@?$CComObject@VCSMBHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CSMBHelperClass>::Release(void)
```
