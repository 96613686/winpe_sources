# __scrt_initialize_onexit_tables

- ea: `0x180001768`
- end: `0x1800017f3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001628`

## callees

- `0x180001768`
- `0x180001908`
- `0x180001c58`
- `0x180001cda`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800B33B0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800B3398._first = *(_OWORD *)&Table._first;
      stru_1800B3398._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800B3398) )
    {
      return 0;
    }
    byte_1800B33B0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001768  push    rbx
0x18000176a  sub     rsp, 20h
0x18000176e  cmp     cs:byte_1800B33B0, 0
0x180001775  mov     ebx, ecx
0x180001777  jnz     short loc_1800017E0
0x180001779  cmp     ecx, 1
0x18000177c  ja      short loc_1800017E8
0x18000177e  call    __scrt_is_ucrt_dll_in_use
0x180001783  test    eax, eax
0x180001785  jz      short loc_1800017AF
0x180001787  test    ebx, ebx
0x180001789  jnz     short loc_1800017AF
0x18000178b  lea     rcx, Table; Table
0x180001792  call    _initialize_onexit_table
0x180001797  test    eax, eax
0x180001799  jnz     short loc_1800017AB
0x18000179b  lea     rcx, stru_1800B3398; Table
0x1800017a2  call    _initialize_onexit_table
0x1800017a7  test    eax, eax
0x1800017a9  jz      short loc_1800017D9
0x1800017ab  xor     al, al
0x1800017ad  jmp     short loc_1800017E2
0x1800017af  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800017b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017bb  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800017c3  mov     cs:Table._end, rax
0x1800017ca  movdqu  xmmword ptr cs:stru_1800B3398._first, xmm0
0x1800017d2  mov     cs:stru_1800B3398._end, rax
0x1800017d9  mov     cs:byte_1800B33B0, 1
0x1800017e0  mov     al, 1
0x1800017e2  add     rsp, 20h
0x1800017e6  pop     rbx
0x1800017e7  retn
0x1800017e8  mov     ecx, 5
0x1800017ed  call    __scrt_fastfail
```
