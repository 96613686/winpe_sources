# _CEnumSubCommands::Next_::_1_::dtor$2

- ea: `0x18000b9d6`
- end: `0x18000b9e2`
- name: `_CEnumSubCommands::Next_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Next_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 72);
}

```

## disassembly

```asm
0x18000b9d6  lea     rcx, [rdx+48h]
0x18000b9dd  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
