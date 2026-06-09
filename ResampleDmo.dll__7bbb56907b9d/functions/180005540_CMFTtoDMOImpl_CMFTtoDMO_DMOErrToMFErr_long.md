# CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)

- ea: `0x180005540`
- end: `0x180005570`
- name: `?DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z`
- size: `48`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180005110`
- `0x180005200`
- `0x1800052f0`
- `0x180005320`
- `0x180005410`
- `0x180005440`
- `0x18000971c`
- `0x18006b4c0`
- `0x18006b5b0`
- `0x18006b660`

## callees

- `0x180005540`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(__int64 a1, unsigned int a2)
{
  unsigned int i; // ecx
  __int64 v4; // rax

  if ( a2 )
  {
    for ( i = 0; i < 6; ++i )
    {
      v4 = (int)i;
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v4]) == a2 )
        return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v4]);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180005540  test    edx, edx
0x180005542  jnz     short loc_180005547
0x180005544  mov     eax, edx
0x180005546  retn
0x180005547  xor     ecx, ecx
0x180005549  lea     r8, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180005550  cmp     ecx, 6
0x180005553  jnb     short loc_180005544
0x180005555  movsxd  rax, ecx
0x180005558  lea     rax, ds:0[rax*8]
0x180005560  cmp     [rax+r8], edx
0x180005564  jz      short loc_18000556A
0x180005566  inc     ecx
0x180005568  jmp     short loc_180005550
0x18000556a  mov     eax, [rax+r8+4]
0x18000556f  retn
```
