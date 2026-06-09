# _CEnumSubCommands::Skip_::_1_::dtor$0

- ea: `0x18000b910`
- end: `0x18000b91c`
- name: `_CEnumSubCommands::Skip_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Skip_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 80);
}

```

## disassembly

```asm
0x18000b910  lea     rcx, [rdx+50h]
0x18000b917  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
