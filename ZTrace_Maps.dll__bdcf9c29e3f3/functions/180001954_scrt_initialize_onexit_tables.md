# __scrt_initialize_onexit_tables

- ea: `0x180001954`
- end: `0x1800019df`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001814`

## callees

- `0x180001954`
- `0x180001c5c`
- `0x180002190`
- `0x180002282`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180007210 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800071F8._first = *(_OWORD *)&Table._first;
      stru_1800071F8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800071F8) )
    {
      return 0;
    }
    byte_180007210 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001954  push    rbx
0x180001956  sub     rsp, 20h
0x18000195a  cmp     cs:byte_180007210, 0
0x180001961  mov     ebx, ecx
0x180001963  jnz     short loc_1800019CC
0x180001965  cmp     ecx, 1
0x180001968  ja      short loc_1800019D4
0x18000196a  call    __scrt_is_ucrt_dll_in_use
0x18000196f  test    eax, eax
0x180001971  jz      short loc_18000199B
0x180001973  test    ebx, ebx
0x180001975  jnz     short loc_18000199B
0x180001977  lea     rcx, Table; Table
0x18000197e  call    _initialize_onexit_table
0x180001983  test    eax, eax
0x180001985  jnz     short loc_180001997
0x180001987  lea     rcx, stru_1800071F8; Table
0x18000198e  call    _initialize_onexit_table
0x180001993  test    eax, eax
0x180001995  jz      short loc_1800019C5
0x180001997  xor     al, al
0x180001999  jmp     short loc_1800019CE
0x18000199b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800019a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800019a7  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800019af  mov     cs:Table._end, rax
0x1800019b6  movdqu  xmmword ptr cs:stru_1800071F8._first, xmm0
0x1800019be  mov     cs:stru_1800071F8._end, rax
0x1800019c5  mov     cs:byte_180007210, 1
0x1800019cc  mov     al, 1
0x1800019ce  add     rsp, 20h
0x1800019d2  pop     rbx
0x1800019d3  retn
0x1800019d4  mov     ecx, 5
0x1800019d9  call    __scrt_fastfail
```
