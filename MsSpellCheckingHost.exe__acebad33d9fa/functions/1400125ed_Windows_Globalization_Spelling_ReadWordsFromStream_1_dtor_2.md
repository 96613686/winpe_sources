# _Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$2

- ea: `0x1400125ed`
- end: `0x1400125f9`
- name: `_Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400087c4`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 96);
}

```

## disassembly

```asm
0x1400125ed  lea     rcx, [rdx+60h]
0x1400125f4  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
