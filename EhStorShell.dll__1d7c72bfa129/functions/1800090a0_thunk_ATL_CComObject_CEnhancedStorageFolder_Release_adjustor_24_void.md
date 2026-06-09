# [thunk]:ATL::CComObject<CEnhancedStorageFolder>::Release`adjustor{24}' (void)

- ea: `0x1800090a0`
- end: `0x1800090a9`
- name: `?Release@?$CComObject@VCEnhancedStorageFolder@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CEnhancedStorageFolder>::Release((_DWORD *)(a1 - 24));
}

```

## disassembly

```asm
0x1800090a0  sub     rcx, 18h
0x1800090a4  jmp     ?Release@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAKXZ; ATL::CComObject<CEnhancedStorageFolder>::Release(void)
```
