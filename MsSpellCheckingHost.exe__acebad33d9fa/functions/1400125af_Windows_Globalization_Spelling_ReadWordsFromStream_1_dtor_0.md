# _Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$0

- ea: `0x1400125af`
- end: `0x1400125d5`
- name: `_Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140008820`
- `0x1400125af`

## pseudocode

```c
void __fastcall Windows::Globalization::Spelling::ReadWordsFromStream_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(*(void ***)(a2 + 56));
  }
}

```

## disassembly

```asm
0x1400125af  push    rbp
0x1400125b1  sub     rsp, 20h
0x1400125b5  mov     rbp, rdx
0x1400125b8  mov     eax, [rbp+30h]
0x1400125bb  and     eax, 1
0x1400125be  test    eax, eax
0x1400125c0  jz      short loc_1400125CF
0x1400125c2  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x1400125c6  mov     rcx, [rbp+38h]
0x1400125ca  call    ??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x1400125cf  add     rsp, 20h
0x1400125d3  pop     rbp
0x1400125d4  retn
```
