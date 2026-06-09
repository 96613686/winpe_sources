# bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b4c8`
- end: `0x18001b4e0`
- name: `??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
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

- `0x180010ed8`
- `0x18001b4c8`

## pseudocode

```c
__int64 __fastcall bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<double,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b4c8  sub     rsp, 28h
0x18001b4cc  cmp     byte ptr [rcx+8], 0
0x18001b4d0  jz      short loc_18001B4DB
0x18001b4d2  mov     rcx, [rcx]
0x18001b4d5  call    ??$Skip@NV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<double,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b4da  nop
0x18001b4db  add     rsp, 28h
0x18001b4df  retn
```
