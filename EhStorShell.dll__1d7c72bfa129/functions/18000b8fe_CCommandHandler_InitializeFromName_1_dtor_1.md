# _CCommandHandler::InitializeFromName_::_1_::dtor$1

- ea: `0x18000b8fe`
- end: `0x18000b90a`
- name: `_CCommandHandler::InitializeFromName_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CCommandHandler::InitializeFromName_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 48);
}

```

## disassembly

```asm
0x18000b8fe  lea     rcx, [rdx+30h]
0x18000b905  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
