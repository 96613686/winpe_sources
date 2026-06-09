# __scrt_initialize_onexit_tables

- ea: `0x180001754`
- end: `0x1800017df`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001614`

## callees

- `0x180001754`
- `0x1800018f4`
- `0x180001c44`
- `0x180001cee`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800070F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800070D8._first = *(_OWORD *)&Table._first;
      stru_1800070D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800070D8) )
    {
      return 0;
    }
    byte_1800070F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001754  push    rbx
0x180001756  sub     rsp, 20h
0x18000175a  cmp     cs:byte_1800070F0, 0
0x180001761  mov     ebx, ecx
0x180001763  jnz     short loc_1800017CC
0x180001765  cmp     ecx, 1
0x180001768  ja      short loc_1800017D4
0x18000176a  call    __scrt_is_ucrt_dll_in_use
0x18000176f  test    eax, eax
0x180001771  jz      short loc_18000179B
0x180001773  test    ebx, ebx
0x180001775  jnz     short loc_18000179B
0x180001777  lea     rcx, Table; Table
0x18000177e  call    _initialize_onexit_table
0x180001783  test    eax, eax
0x180001785  jnz     short loc_180001797
0x180001787  lea     rcx, stru_1800070D8; Table
0x18000178e  call    _initialize_onexit_table
0x180001793  test    eax, eax
0x180001795  jz      short loc_1800017C5
0x180001797  xor     al, al
0x180001799  jmp     short loc_1800017CE
0x18000179b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800017a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017a7  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800017af  mov     cs:Table._end, rax
0x1800017b6  movdqu  xmmword ptr cs:stru_1800070D8._first, xmm0
0x1800017be  mov     cs:stru_1800070D8._end, rax
0x1800017c5  mov     cs:byte_1800070F0, 1
0x1800017cc  mov     al, 1
0x1800017ce  add     rsp, 20h
0x1800017d2  pop     rbx
0x1800017d3  retn
0x1800017d4  mov     ecx, 5
0x1800017d9  call    __scrt_fastfail
```
