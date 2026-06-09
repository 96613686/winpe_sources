# bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001b528`
- end: `0x18001b540`
- name: `??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `38`
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
- `0x18000d8e4`
- `0x18000d9c4`
- `0x18000daa8`
- `0x18000dd18`
- `0x18000de00`
- `0x18000df8c`
- `0x18000e060`
- `0x18000e134`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000e3a4`
- `0x18000e564`
- `0x18000e728`
- `0x18000e7fc`
- `0x18000e9c0`
- `0x18000ea94`
- `0x18000eb64`
- `0x18000ec38`
- `0x18000ef58`
- `0x18000f194`
- `0x18000f4c8`
- `0x18000f61c`
- `0x18000f6ec`
- `0x18001b45c`
- `0x18001be18`
- `0x18001beec`
- `0x18001bfc0`
- `0x18001c088`
- `0x18001c15c`
- `0x18001c5c0`
- `0x18001c694`

## callees

- `0x180010f64`
- `0x18001b528`

## pseudocode

```c
__int64 __fastcall bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<bool,bond::CompactBinaryReader<bond::InputBuffer>>(*(bond::InputBuffer **)a1);
  return result;
}

```

## disassembly

```asm
0x18001b528  sub     rsp, 28h
0x18001b52c  cmp     byte ptr [rcx+8], 0
0x18001b530  jz      short loc_18001B53B
0x18001b532  mov     rcx, [rcx]
0x18001b535  call    ??$Skip@_NV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<bool,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001b53a  nop
0x18001b53b  add     rsp, 28h
0x18001b53f  retn
```
