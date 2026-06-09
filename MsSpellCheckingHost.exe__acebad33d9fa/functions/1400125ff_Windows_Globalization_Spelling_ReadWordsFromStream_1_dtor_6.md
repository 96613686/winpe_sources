# _Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$6

- ea: `0x1400125ff`
- end: `0x14001260b`
- name: `_Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400087c4`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 128);
}

```

## disassembly

```asm
0x1400125ff  lea     rcx, [rdx+80h]
0x140012606  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
