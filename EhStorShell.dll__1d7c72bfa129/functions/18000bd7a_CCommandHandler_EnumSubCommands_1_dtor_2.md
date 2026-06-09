# _CCommandHandler::EnumSubCommands_::_1_::dtor$2

- ea: `0x18000bd7a`
- end: `0x18000bd86`
- name: `_CCommandHandler::EnumSubCommands_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CCommandHandler::EnumSubCommands_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 96);
}

```

## disassembly

```asm
0x18000bd7a  lea     rcx, [rdx+60h]
0x18000bd81  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
