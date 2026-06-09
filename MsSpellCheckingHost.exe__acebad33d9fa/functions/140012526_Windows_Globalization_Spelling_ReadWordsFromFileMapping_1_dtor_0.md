# _Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$0

- ea: `0x140012526`
- end: `0x14001254f`
- name: `_Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor$0`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140008820`
- `0x140012526`

## pseudocode

```c
void __fastcall Windows::Globalization::Spelling::ReadWordsFromFileMapping_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 64) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(*(void ***)(a2 + 136));
  }
}

```

## disassembly

```asm
0x140012526  push    rbp
0x140012528  sub     rsp, 20h
0x14001252c  mov     rbp, rdx
0x14001252f  mov     eax, [rbp+40h]
0x140012532  and     eax, 1
0x140012535  test    eax, eax
0x140012537  jz      short loc_140012549
0x140012539  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x14001253d  mov     rcx, [rbp+88h]
0x140012544  call    ??1?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring const,std::wstring>::~map<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>>(void)
0x140012549  add     rsp, 20h
0x14001254d  pop     rbp
0x14001254e  retn
```
