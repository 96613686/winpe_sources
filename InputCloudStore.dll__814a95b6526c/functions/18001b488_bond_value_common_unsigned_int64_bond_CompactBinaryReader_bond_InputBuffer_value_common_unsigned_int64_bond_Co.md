# bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b488`
- end: `0x18001b4a0`
- name: `??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
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
- `0x18000db90`
- `0x18000dc54`
- `0x18000ded8`
- `0x18000ede0`
- `0x18000f7c0`
- `0x18001b444`
- `0x18001c224`
- `0x18001c36c`
- `0x18001c420`

## callees

- `0x180010e90`
- `0x18001b488`

## pseudocode

```c
unsigned __int64 __fastcall bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  unsigned __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<short,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b488  sub     rsp, 28h
0x18001b48c  cmp     byte ptr [rcx+8], 0
0x18001b490  jz      short loc_18001B49B
0x18001b492  mov     rcx, [rcx]
0x18001b495  call    ??$Skip@FV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<short,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b49a  nop
0x18001b49b  add     rsp, 28h
0x18001b49f  retn
```
