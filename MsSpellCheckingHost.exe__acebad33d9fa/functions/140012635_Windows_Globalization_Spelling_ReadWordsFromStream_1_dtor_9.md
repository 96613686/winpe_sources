# _Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$9

- ea: `0x140012635`
- end: `0x140012641`
- name: `_Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010ad4`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(a2 + 160);
}

```

## disassembly

```asm
0x140012635  lea     rcx, [rdx+0A0h]
0x14001263c  jmp     ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
```
