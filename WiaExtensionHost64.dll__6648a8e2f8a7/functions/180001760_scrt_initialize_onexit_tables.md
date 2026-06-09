# __scrt_initialize_onexit_tables

- ea: `0x180001760`
- end: `0x1800017eb`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001620`

## callees

- `0x180001760`
- `0x180001900`
- `0x180001c54`
- `0x180001ce6`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800050F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800050D8._first = *(_OWORD *)&Table._first;
      stru_1800050D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800050D8) )
    {
      return 0;
    }
    byte_1800050F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001760  push    rbx
0x180001762  sub     rsp, 20h
0x180001766  cmp     cs:byte_1800050F0, 0
0x18000176d  mov     ebx, ecx
0x18000176f  jnz     short loc_1800017D8
0x180001771  cmp     ecx, 1
0x180001774  ja      short loc_1800017E0
0x180001776  call    __scrt_is_ucrt_dll_in_use
0x18000177b  test    eax, eax
0x18000177d  jz      short loc_1800017A7
0x18000177f  test    ebx, ebx
0x180001781  jnz     short loc_1800017A7
0x180001783  lea     rcx, Table; Table
0x18000178a  call    _initialize_onexit_table
0x18000178f  test    eax, eax
0x180001791  jnz     short loc_1800017A3
0x180001793  lea     rcx, stru_1800050D8; Table
0x18000179a  call    _initialize_onexit_table
0x18000179f  test    eax, eax
0x1800017a1  jz      short loc_1800017D1
0x1800017a3  xor     al, al
0x1800017a5  jmp     short loc_1800017DA
0x1800017a7  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800017af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017b3  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800017bb  mov     cs:Table._end, rax
0x1800017c2  movdqu  xmmword ptr cs:stru_1800050D8._first, xmm0
0x1800017ca  mov     cs:stru_1800050D8._end, rax
0x1800017d1  mov     cs:byte_1800050F0, 1
0x1800017d8  mov     al, 1
0x1800017da  add     rsp, 20h
0x1800017de  pop     rbx
0x1800017df  retn
0x1800017e0  mov     ecx, 5
0x1800017e5  call    __scrt_fastfail
```
