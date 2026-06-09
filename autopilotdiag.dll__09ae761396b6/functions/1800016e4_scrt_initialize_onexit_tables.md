# __scrt_initialize_onexit_tables

- ea: `0x1800016e4`
- end: `0x18000176f`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015a4`

## callees

- `0x1800016e4`
- `0x180001884`
- `0x180001bb0`
- `0x180001c3a`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800040F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800040D8._first = *(_OWORD *)&Table._first;
      stru_1800040D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800040D8) )
    {
      return 0;
    }
    byte_1800040F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x1800016e4  push    rbx
0x1800016e6  sub     rsp, 20h
0x1800016ea  cmp     cs:byte_1800040F0, 0
0x1800016f1  mov     ebx, ecx
0x1800016f3  jnz     short loc_18000175C
0x1800016f5  cmp     ecx, 1
0x1800016f8  ja      short loc_180001764
0x1800016fa  call    __scrt_is_ucrt_dll_in_use
0x1800016ff  test    eax, eax
0x180001701  jz      short loc_18000172B
0x180001703  test    ebx, ebx
0x180001705  jnz     short loc_18000172B
0x180001707  lea     rcx, Table; Table
0x18000170e  call    _initialize_onexit_table
0x180001713  test    eax, eax
0x180001715  jnz     short loc_180001727
0x180001717  lea     rcx, stru_1800040D8; Table
0x18000171e  call    _initialize_onexit_table
0x180001723  test    eax, eax
0x180001725  jz      short loc_180001755
0x180001727  xor     al, al
0x180001729  jmp     short loc_18000175E
0x18000172b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001733  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001737  movdqu  xmmword ptr cs:Table._first, xmm0
0x18000173f  mov     cs:Table._end, rax
0x180001746  movdqu  xmmword ptr cs:stru_1800040D8._first, xmm0
0x18000174e  mov     cs:stru_1800040D8._end, rax
0x180001755  mov     cs:byte_1800040F0, 1
0x18000175c  mov     al, 1
0x18000175e  add     rsp, 20h
0x180001762  pop     rbx
0x180001763  retn
0x180001764  mov     ecx, 5
0x180001769  call    __scrt_fastfail
```
