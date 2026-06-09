# _Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$5

- ea: `0x140012579`
- end: `0x140012585`
- name: `_Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008820`

## pseudocode

```c
void __fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>((void **)(a2 + 48));
}

```

## disassembly

```asm
0x140012579  lea     rcx, [rdx+30h]
0x140012580  jmp     ??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
```
