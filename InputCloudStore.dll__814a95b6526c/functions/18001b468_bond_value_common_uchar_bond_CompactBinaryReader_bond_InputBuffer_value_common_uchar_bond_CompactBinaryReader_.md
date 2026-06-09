# bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b468`
- end: `0x18001b480`
- name: `??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
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
- `0x18001b438`

## callees

- `0x180010e74`
- `0x18001b468`

## pseudocode

```c
__int64 __fastcall bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<unsigned char,bond::CompactBinaryReader<bond::InputBuffer>>(*(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x18001b468  sub     rsp, 28h
0x18001b46c  cmp     byte ptr [rcx+8], 0
0x18001b470  jz      short loc_18001B47B
0x18001b472  mov     rcx, [rcx]
0x18001b475  call    ??$Skip@EV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<uchar,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b47a  nop
0x18001b47b  add     rsp, 28h
0x18001b47f  retn
```
