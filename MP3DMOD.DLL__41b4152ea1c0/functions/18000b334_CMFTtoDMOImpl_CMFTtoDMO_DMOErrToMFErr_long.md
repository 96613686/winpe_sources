# CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)

- ea: `0x18000b334`
- end: `0x18000b35d`
- name: `?DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7e0`
- `0x18000a8d0`
- `0x18000a900`
- `0x18000aa00`
- `0x18000aaf0`
- `0x18000abf0`
- `0x18000ae10`
- `0x18000ae90`
- `0x18000d2dc`
- `0x18000f640`
- `0x18000f730`
- `0x18000f760`
- `0x18000f810`

## callees

- `0x18000b334`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(__int64 a1, unsigned int a2)
{
  unsigned int i; // eax

  if ( a2 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[i]) == a2 )
        return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[i]);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000b334  test    edx, edx
0x18000b336  jnz     short loc_18000B33B
0x18000b338  mov     eax, edx
0x18000b33a  retn
0x18000b33b  xor     eax, eax
0x18000b33d  lea     r8, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x18000b344  cmp     eax, 6
0x18000b347  jnb     short loc_18000B338
0x18000b349  movsxd  rcx, eax
0x18000b34c  cmp     [r8+rcx*8], edx
0x18000b350  jz      short loc_18000B356
0x18000b352  inc     eax
0x18000b354  jmp     short loc_18000B344
0x18000b356  mov     edx, [r8+rcx*8+4]
0x18000b35b  jmp     short loc_18000B338
```
