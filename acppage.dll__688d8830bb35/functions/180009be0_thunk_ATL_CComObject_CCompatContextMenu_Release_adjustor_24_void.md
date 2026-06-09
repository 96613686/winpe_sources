# [thunk]:ATL::CComObject<CCompatContextMenu>::Release`adjustor{24}' (void)

- ea: `0x180009be0`
- end: `0x180009be9`
- name: `?Release@?$CComObject@VCCompatContextMenu@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CCompatContextMenu>::Release((volatile signed __int32 *)(a1 - 24));
}

```

## disassembly

```asm
0x180009be0  sub     rcx, 18h
0x180009be4  jmp     ?Release@?$CComObject@VCCompatContextMenu@@@ATL@@UEAAKXZ; ATL::CComObject<CCompatContextMenu>::Release(void)
```
