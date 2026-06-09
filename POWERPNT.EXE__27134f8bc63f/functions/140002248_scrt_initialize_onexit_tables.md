# __scrt_initialize_onexit_tables

- ea: `0x140002248`
- end: `0x1400022d3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001d40`

## callees

- `0x140002248`
- `0x1400022d4`
- `0x1400024fc`
- `0x140002941`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1400050C8 )
  {
    if ( a1 > 1 )
    {
      _scrt_fastfail(5u);
      __debugbreak();
    }
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1400050E8._first = *(_OWORD *)&Table._first;
      stru_1400050E8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table_0(&Table) || initialize_onexit_table_0(&stru_1400050E8) )
    {
      return 0;
    }
    byte_1400050C8 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140002248  push    rbx
0x14000224a  sub     rsp, 20h
0x14000224e  cmp     cs:byte_1400050C8, 0
0x140002255  mov     ebx, ecx
0x140002257  jnz     short loc_1400022C0
0x140002259  cmp     ecx, 1
0x14000225c  ja      short loc_1400022C8
0x14000225e  call    __scrt_is_ucrt_dll_in_use
0x140002263  test    eax, eax
0x140002265  jz      short loc_14000228F
0x140002267  test    ebx, ebx
0x140002269  jnz     short loc_14000228F
0x14000226b  lea     rcx, Table; Table
0x140002272  call    _initialize_onexit_table_0
0x140002277  test    eax, eax
0x140002279  jnz     short loc_14000228B
0x14000227b  lea     rcx, stru_1400050E8; Table
0x140002282  call    _initialize_onexit_table_0
0x140002287  test    eax, eax
0x140002289  jz      short loc_1400022B9
0x14000228b  xor     al, al
0x14000228d  jmp     short loc_1400022C2
0x14000228f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140002297  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000229b  movdqu  xmmword ptr cs:Table._first, xmm0
0x1400022a3  mov     cs:Table._end, rax
0x1400022aa  movdqu  xmmword ptr cs:stru_1400050E8._first, xmm0
0x1400022b2  mov     cs:stru_1400050E8._end, rax
0x1400022b9  mov     cs:byte_1400050C8, 1
0x1400022c0  mov     al, 1
0x1400022c2  add     rsp, 20h
0x1400022c6  pop     rbx
0x1400022c7  retn
0x1400022c8  mov     ecx, 5
0x1400022cd  call    __scrt_fastfail
0x1400022d2  int     3; Trap to Debugger
```
