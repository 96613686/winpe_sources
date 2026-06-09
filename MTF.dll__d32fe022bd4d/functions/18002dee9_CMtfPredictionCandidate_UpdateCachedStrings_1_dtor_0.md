# _CMtfPredictionCandidate::_UpdateCachedStrings_::_1_::dtor$0

- ea: `0x18002dee9`
- end: `0x18002def5`
- name: `_CMtfPredictionCandidate::_UpdateCachedStrings_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000e5cc`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::_UpdateCachedStrings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 224);
}

```

## disassembly

```asm
0x18002dee9  lea     rcx, [rdx+0E0h]
0x18002def0  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
