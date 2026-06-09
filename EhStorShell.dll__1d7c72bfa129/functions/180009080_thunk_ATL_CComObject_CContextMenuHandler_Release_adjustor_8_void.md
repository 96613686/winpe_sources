# [thunk]:ATL::CComObject<CContextMenuHandler>::Release`adjustor{8}' (void)

- ea: `0x180009080`
- end: `0x180009089`
- name: `?Release@?$CComObject@VCContextMenuHandler@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800044b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::Release(__int64 a1)
{
  return ATL::CComObject<CContextMenuHandler>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x180009080  sub     rcx, 8
0x180009084  jmp     ?Release@?$CComObject@VCContextMenuHandler@@@ATL@@UEAAKXZ; ATL::CComObject<CContextMenuHandler>::Release(void)
```
