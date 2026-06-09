# [thunk]:ATL::CComObject<CCompatContextMenu>::Release`adjustor{16}' (void)

- ea: `0x180009bd0`
- end: `0x180009bd9`
- name: `?Release@?$CComObject@VCCompatContextMenu@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009b30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCompatContextMenu>::Release(__int64 a1)
{
  return ATL::CComObject<CCompatContextMenu>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x180009bd0  sub     rcx, 10h
0x180009bd4  jmp     ?Release@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ; ATL::CComObject<CCompatContextMenu>::Release(void)
```
