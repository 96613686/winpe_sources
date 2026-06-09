# __scrt_initialize_onexit_tables

- ea: `0x180003c20`
- end: `0x180003cab`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800035f0`
- `0x180003ad8`

## callees

- `0x180003c20`
- `0x180003df8`
- `0x1800042e4`
- `0x180004344`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180007269 )
  {
    if ( a1 > 1 )
    {
      _scrt_fastfail(5u);
      JUMPOUT(0x180003CAALL);
    }
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_180007288._first = *(_OWORD *)&Table._first;
      stru_180007288._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table_0(&Table) || initialize_onexit_table_0(&stru_180007288) )
    {
      return 0;
    }
    byte_180007269 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180003c20  push    rbx
0x180003c22  sub     rsp, 20h
0x180003c26  cmp     cs:byte_180007269, 0
0x180003c2d  mov     ebx, ecx
0x180003c2f  jnz     short loc_180003C98
0x180003c31  cmp     ecx, 1
0x180003c34  ja      short loc_180003CA0
0x180003c36  call    __scrt_is_ucrt_dll_in_use
0x180003c3b  test    eax, eax
0x180003c3d  jz      short loc_180003C67
0x180003c3f  test    ebx, ebx
0x180003c41  jnz     short loc_180003C67
0x180003c43  lea     rcx, Table; Table
0x180003c4a  call    _initialize_onexit_table_0
0x180003c4f  test    eax, eax
0x180003c51  jnz     short loc_180003C63
0x180003c53  lea     rcx, stru_180007288; Table
0x180003c5a  call    _initialize_onexit_table_0
0x180003c5f  test    eax, eax
0x180003c61  jz      short loc_180003C91
0x180003c63  xor     al, al
0x180003c65  jmp     short loc_180003C9A
0x180003c67  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180003c6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003c73  movdqu  xmmword ptr cs:Table._first, xmm0
0x180003c7b  mov     cs:Table._end, rax
0x180003c82  movdqu  xmmword ptr cs:stru_180007288._first, xmm0
0x180003c8a  mov     cs:stru_180007288._end, rax
0x180003c91  mov     cs:byte_180007269, 1
0x180003c98  mov     al, 1
0x180003c9a  add     rsp, 20h
0x180003c9e  pop     rbx
0x180003c9f  retn
0x180003ca0  mov     ecx, 5
0x180003ca5  call    __scrt_fastfail
```
