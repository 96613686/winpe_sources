# _CEnhancedStorageFolder::CreateItemFromData_::_1_::dtor$0

- ea: `0x18000b860`
- end: `0x18000b86c`
- name: `_CEnhancedStorageFolder::CreateItemFromData_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageFolder::CreateItemFromData_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 32);
}

```

## disassembly

```asm
0x18000b860  lea     rcx, [rdx+20h]
0x18000b867  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
