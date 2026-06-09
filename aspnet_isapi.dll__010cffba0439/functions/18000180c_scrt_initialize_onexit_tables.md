# __scrt_initialize_onexit_tables

- ea: `0x18000180c`
- end: `0x180001897`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800016c4`

## callees

- `0x18000180c`
- `0x180001990`
- `0x180001e94`
- `0x180001ed0`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180003081 )
  {
    if ( a1 > 1 )
    {
      _scrt_fastfail(5u);
      JUMPOUT(0x180001896LL);
    }
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800030A0._first = *(_OWORD *)&Table._first;
      stru_1800030A0._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table_0(&Table) || initialize_onexit_table_0(&stru_1800030A0) )
    {
      return 0;
    }
    byte_180003081 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x18000180c  push    rbx
0x18000180e  sub     rsp, 20h
0x180001812  cmp     cs:byte_180003081, 0
0x180001819  mov     ebx, ecx
0x18000181b  jnz     short loc_180001884
0x18000181d  cmp     ecx, 1
0x180001820  ja      short loc_18000188C
0x180001822  call    __scrt_is_ucrt_dll_in_use
0x180001827  test    eax, eax
0x180001829  jz      short loc_180001853
0x18000182b  test    ebx, ebx
0x18000182d  jnz     short loc_180001853
0x18000182f  lea     rcx, Table; Table
0x180001836  call    _initialize_onexit_table_0
0x18000183b  test    eax, eax
0x18000183d  jnz     short loc_18000184F
0x18000183f  lea     rcx, stru_1800030A0; Table
0x180001846  call    _initialize_onexit_table_0
0x18000184b  test    eax, eax
0x18000184d  jz      short loc_18000187D
0x18000184f  xor     al, al
0x180001851  jmp     short loc_180001886
0x180001853  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000185b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000185f  movdqu  xmmword ptr cs:Table._first, xmm0
0x180001867  mov     cs:Table._end, rax
0x18000186e  movdqu  xmmword ptr cs:stru_1800030A0._first, xmm0
0x180001876  mov     cs:stru_1800030A0._end, rax
0x18000187d  mov     cs:byte_180003081, 1
0x180001884  mov     al, 1
0x180001886  add     rsp, 20h
0x18000188a  pop     rbx
0x18000188b  retn
0x18000188c  mov     ecx, 5
0x180001891  call    __scrt_fastfail
```
