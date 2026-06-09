# bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)

- ea: `0x18001363c`
- end: `0x180013654`
- name: `??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f45c`
- `0x18000fbc0`
- `0x18000fca4`
- `0x18000fd78`
- `0x18000fe4c`
- `0x180010080`
- `0x180013570`
- `0x180017910`
- `0x180017dd8`
- `0x180017ebc`
- `0x180017f90`
- `0x180018064`
- `0x1800182a0`
- `0x180018374`
- `0x180019790`
- `0x18001adac`
- `0x18001afdc`

## callees

- `0x18001066c`
- `0x18001363c`

## pseudocode

```c
__int64 __fastcall bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 8) )
    return bond::Skip<bool,bond::CompactBinaryReader<bond::InputBuffer>>(*(_QWORD *)a1);
  return result;
}

```

## disassembly

```asm
0x18001363c  sub     rsp, 28h
0x180013640  cmp     byte ptr [rcx+8], 0
0x180013644  jz      short loc_18001364F
0x180013646  mov     rcx, [rcx]
0x180013649  call    ??$Skip@_NV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@YAXAEAV?$CompactBinaryReader@VInputBuffer@bond@@@0@AEBUnothrow_t@std@@@Z; bond::Skip<bool,bond::CompactBinaryReader<bond::InputBuffer>>(bond::CompactBinaryReader<bond::InputBuffer> &,std::nothrow_t const &)
0x18001364e  nop
0x18001364f  add     rsp, 28h
0x180013653  retn
```
