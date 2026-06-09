# CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)

- ea: `0x18001e360`
- end: `0x18001e389`
- name: `?DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18001da00`
- `0x18001daf0`
- `0x18001dbf0`
- `0x18001dde0`
- `0x18001dea0`
- `0x1800280ac`
- `0x18002d190`
- `0x18002d280`
- `0x18002d2b0`
- `0x18002d360`
- `0x18002d450`
- `0x18002d480`
- `0x18002d510`

## callees

- `0x18001e360`

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
0x18001e360  test    edx, edx
0x18001e362  jnz     short loc_18001E367
0x18001e364  mov     eax, edx
0x18001e366  retn
0x18001e367  xor     eax, eax
0x18001e369  lea     r8, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x18001e370  cmp     eax, 6
0x18001e373  jnb     short loc_18001E364
0x18001e375  movsxd  rcx, eax
0x18001e378  cmp     [r8+rcx*8], edx
0x18001e37c  jz      short loc_18001E382
0x18001e37e  inc     eax
0x18001e380  jmp     short loc_18001E370
0x18001e382  mov     edx, [r8+rcx*8+4]
0x18001e387  jmp     short loc_18001E364
```
