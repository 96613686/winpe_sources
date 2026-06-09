# __scrt_initialize_onexit_tables

- ea: `0x180001738`
- end: `0x1800017c3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015f8`

## callees

- `0x180001738`
- `0x1800018d8`
- `0x180001e20`
- `0x180001f22`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180013490 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_180013478._first = *(_OWORD *)&Table._first;
      stru_180013478._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_180013478) )
    {
      return 0;
    }
    byte_180013490 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001738  push    rbx
0x18000173a  sub     rsp, 20h
0x18000173e  cmp     cs:byte_180013490, 0
0x180001745  mov     ebx, ecx
0x180001747  jnz     short loc_1800017B0
0x180001749  cmp     ecx, 1
0x18000174c  ja      short loc_1800017B8
0x18000174e  call    __scrt_is_ucrt_dll_in_use
0x180001753  test    eax, eax
0x180001755  jz      short loc_18000177F
0x180001757  test    ebx, ebx
0x180001759  jnz     short loc_18000177F
0x18000175b  lea     rcx, Table; Table
0x180001762  call    _initialize_onexit_table
0x180001767  test    eax, eax
0x180001769  jnz     short loc_18000177B
0x18000176b  lea     rcx, stru_180013478; Table
0x180001772  call    _initialize_onexit_table
0x180001777  test    eax, eax
0x180001779  jz      short loc_1800017A9
0x18000177b  xor     al, al
0x18000177d  jmp     short loc_1800017B2
0x18000177f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001787  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000178b  movdqu  xmmword ptr cs:Table._first, xmm0
0x180001793  mov     cs:Table._end, rax
0x18000179a  movdqu  xmmword ptr cs:stru_180013478._first, xmm0
0x1800017a2  mov     cs:stru_180013478._end, rax
0x1800017a9  mov     cs:byte_180013490, 1
0x1800017b0  mov     al, 1
0x1800017b2  add     rsp, 20h
0x1800017b6  pop     rbx
0x1800017b7  retn
0x1800017b8  mov     ecx, 5
0x1800017bd  call    __scrt_fastfail
```
