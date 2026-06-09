# _Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$11

- ea: `0x140012623`
- end: `0x14001262f`
- name: `_Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$11`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400087c4`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 160);
}

```

## disassembly

```asm
0x140012623  lea     rcx, [rdx+0A0h]
0x14001262a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
