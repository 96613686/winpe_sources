# _CCommandHandler::EnumSubCommands_::_1_::dtor$1

- ea: `0x18000b7c0`
- end: `0x18000b7cc`
- name: `_CCommandHandler::EnumSubCommands_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CCommandHandler::EnumSubCommands_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 104);
}

```

## disassembly

```asm
0x18000b7c0  lea     rcx, [rdx+68h]
0x18000b7c7  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
