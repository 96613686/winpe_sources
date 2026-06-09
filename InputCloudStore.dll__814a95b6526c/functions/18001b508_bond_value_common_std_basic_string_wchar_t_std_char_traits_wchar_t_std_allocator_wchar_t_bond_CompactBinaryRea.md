# bond::value_common<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b508`
- end: `0x18001b520`
- name: `??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ab38`
- `0x18000ae24`
- `0x18000b018`
- `0x18000b218`
- `0x18000b3fc`
- `0x18000b79c`
- `0x18000ba0c`

## callees

- `0x180010f48`
- `0x18001b508`

## pseudocode

```c
__int64 __fastcall bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<std::wstring,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b508  sub     rsp, 28h
0x18001b50c  cmp     byte ptr [rcx+8], 0
0x18001b510  jz      short loc_18001B51B
0x18001b512  mov     rcx, [rcx]
0x18001b515  call    ??$Skip@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<std::wstring,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b51a  nop
0x18001b51b  add     rsp, 28h
0x18001b51f  retn
```
