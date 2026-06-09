# bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001359c`
- end: `0x1800135b4`
- name: `??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f45c`
- `0x180013564`
- `0x180017910`
- `0x18001adac`
- `0x18001afdc`
- `0x18001bfdc`
- `0x18001c0a0`
- `0x18001c164`
- `0x18001c450`
- `0x18001c768`

## callees

- `0x1800105b4`
- `0x18001359c`

## pseudocode

```c
__int64 __fastcall bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<short,bond::CompactBinaryReader<bond::InputBuffer>>(*(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x18001359c  sub     rsp, 28h
0x1800135a0  cmp     byte ptr [rcx+8], 0
0x1800135a4  jz      short loc_1800135AF
0x1800135a6  mov     rcx, [rcx]
0x1800135a9  call    ??$Skip@FV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<short,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x1800135ae  nop
0x1800135af  add     rsp, 28h
0x1800135b3  retn
```
