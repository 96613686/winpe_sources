# [thunk]:ATL::CComObject<CEnhancedStorageFolder>::AddRef`adjustor{16}' (void)

- ea: `0x180007ea0`
- end: `0x180007ea9`
- name: `?AddRef@?$CComObject@VCEnhancedStorageFolder@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e80`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEnhancedStorageFolder>::AddRef(__int64 a1)
{
  return ATL::CComObject<CEnhancedStorageFolder>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180007ea0  sub     rcx, 10h
0x180007ea4  jmp     ?AddRef@?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAKXZ; ATL::CComObject<CEnhancedStorageFolder>::AddRef(void)
```
