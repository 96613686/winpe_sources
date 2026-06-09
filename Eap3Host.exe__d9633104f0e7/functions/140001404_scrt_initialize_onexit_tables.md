# __scrt_initialize_onexit_tables

- ea: `0x140001404`
- end: `0x14000148f`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001090`

## callees

- `0x140001404`
- `0x140001740`
- `0x140001bfc`
- `0x140001f08`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_140006190 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_140006178._first = *(_OWORD *)&Table._first;
      stru_140006178._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_140006178) )
    {
      return 0;
    }
    byte_140006190 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140001404  push    rbx
0x140001406  sub     rsp, 20h
0x14000140a  cmp     cs:byte_140006190, 0
0x140001411  mov     ebx, ecx
0x140001413  jnz     short loc_14000147C
0x140001415  cmp     ecx, 1
0x140001418  ja      short loc_140001484
0x14000141a  call    __scrt_is_ucrt_dll_in_use
0x14000141f  test    eax, eax
0x140001421  jz      short loc_14000144B
0x140001423  test    ebx, ebx
0x140001425  jnz     short loc_14000144B
0x140001427  lea     rcx, Table; Table
0x14000142e  call    _initialize_onexit_table
0x140001433  test    eax, eax
0x140001435  jnz     short loc_140001447
0x140001437  lea     rcx, stru_140006178; Table
0x14000143e  call    _initialize_onexit_table
0x140001443  test    eax, eax
0x140001445  jz      short loc_140001475
0x140001447  xor     al, al
0x140001449  jmp     short loc_14000147E
0x14000144b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140001453  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001457  movdqu  xmmword ptr cs:Table._first, xmm0
0x14000145f  mov     cs:Table._end, rax
0x140001466  movdqu  xmmword ptr cs:stru_140006178._first, xmm0
0x14000146e  mov     cs:stru_140006178._end, rax
0x140001475  mov     cs:byte_140006190, 1
0x14000147c  mov     al, 1
0x14000147e  add     rsp, 20h
0x140001482  pop     rbx
0x140001483  retn
0x140001484  mov     ecx, 5
0x140001489  call    __scrt_fastfail
```
