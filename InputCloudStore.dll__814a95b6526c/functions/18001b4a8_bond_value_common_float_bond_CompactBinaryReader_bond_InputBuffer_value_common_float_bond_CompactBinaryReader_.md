# bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b4a8`
- end: `0x18001b4c0`
- name: `??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
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
- `0x18000ed0c`
- `0x18000f334`
- `0x18001b450`

## callees

- `0x180010ebc`
- `0x18001b4a8`

## pseudocode

```c
__int64 __fastcall bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<float,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b4a8  sub     rsp, 28h
0x18001b4ac  cmp     byte ptr [rcx+8], 0
0x18001b4b0  jz      short loc_18001B4BB
0x18001b4b2  mov     rcx, [rcx]
0x18001b4b5  call    ??$Skip@MV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<float,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b4ba  nop
0x18001b4bb  add     rsp, 28h
0x18001b4bf  retn
```
