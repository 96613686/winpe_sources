# _CCommandHandler::SetSelection_::_1_::dtor$1

- ea: `0x18000b922`
- end: `0x18000b92e`
- name: `_CCommandHandler::SetSelection_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004530`

## pseudocode

```c
__int64 __fastcall CCommandHandler::SetSelection_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(a2 + 88);
}

```

## disassembly

```asm
0x18000b922  lea     rcx, [rdx+58h]
0x18000b929  jmp     ??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ; ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)
```
