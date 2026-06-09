# [thunk]:ATL::CComObject<CEnhancedStorageFolder>::Release`adjustor{16}' (void)

- ea: `0x180009090`
- end: `0x180009099`
- name: `?Release@?$CComObject@VCEnhancedStorageFolder@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800024f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::Release(__int64 a1)
{
  return ATL::CComObject<CEnhancedStorageFolder>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x180009090  sub     rcx, 10h
0x180009094  jmp     ?Release@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAKXZ; ATL::CComObject<CEnhancedStorageFolder>::Release(void)
```
