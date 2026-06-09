# bond::value_common<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b4e8`
- end: `0x18001b500`
- name: `??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
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

- `0x180010f2c`
- `0x18001b4e8`

## pseudocode

```c
__int64 __fastcall bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<std::string,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b4e8  sub     rsp, 28h
0x18001b4ec  cmp     byte ptr [rcx+8], 0
0x18001b4f0  jz      short loc_18001B4FB
0x18001b4f2  mov     rcx, [rcx]
0x18001b4f5  call    ??$Skip@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<std::string,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b4fa  nop
0x18001b4fb  add     rsp, 28h
0x18001b4ff  retn
```
