# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const)

- ea: `0x1800074d8`
- end: `0x1800075fe`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a5f0`
- `0x180011b90`
- `0x1800127a8`
- `0x180013068`

## callees

- `0x180001c24`
- `0x1800074d8`
- `0x1800078d8`
- `0x180007900`
- `0x180013ab4`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, _WORD *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  size_t v6; // rbx
  size_t v7; // rcx
  void *v8; // rax
  _QWORD *v9; // rsi
  size_t v10; // rbx

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v7 = 2 * (v5 + 1);
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v7 = -2;
    }
    if ( v7 >= 0x1000 )
    {
      if ( v7 + 39 >= v7 )
      {
        v8 = operator new(v7 + 39);
        if ( !v8 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v7);
LABEL_19:
    a1[2] = v4;
    v10 = 2 * v4;
    *a1 = v9;
    a1[3] = v5;
    memcpy_0(v9, a2, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
    return a1;
  }
  a1[2] = v4;
  v6 = 2 * v4;
  a1[3] = 7;
  memcpy_0(a1, a2, v6);
  *(_WORD *)((char *)a1 + v6) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800074d8  push    rbx
0x1800074da  push    rbp
0x1800074db  push    rsi
0x1800074dc  push    rdi
0x1800074dd  push    r14
0x1800074df  push    r15
0x1800074e1  sub     rsp, 28h
0x1800074e5  xor     r15d, r15d
0x1800074e8  xorps   xmm0, xmm0
0x1800074eb  movups  xmmword ptr [rcx], xmm0
0x1800074ee  mov     [rcx+10h], r15
0x1800074f2  mov     r14, rdx
0x1800074f5  mov     [rcx+18h], r15
0x1800074f9  mov     rdi, rcx
0x1800074fc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007500  inc     rbx
0x180007503  cmp     [rdx+rbx*2], r15w
0x180007508  jnz     short loc_180007500
0x18000750a  mov     rbp, 7FFFFFFFFFFFFFFEh
0x180007514  cmp     rbx, rbp
0x180007517  ja      loc_1800075F2
0x18000751d  cmp     rbx, 7
0x180007521  ja      short loc_180007544
0x180007523  mov     [rcx+10h], rbx
0x180007527  add     rbx, rbx
0x18000752a  mov     r8, rbx; Size
0x18000752d  mov     qword ptr [rcx+18h], 7
0x180007535  call    memcpy_0
0x18000753a  mov     [rbx+rdi], r15w
0x18000753f  jmp     loc_1800075E2
0x180007544  mov     rax, rbx
0x180007547  or      rax, 7
0x18000754b  cmp     rax, rbp
0x18000754e  jbe     short loc_18000757F
0x180007550  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180007557  cmp     rcx, 1000h
0x18000755e  jb      short loc_1800075B9
0x180007560  lea     rax, [rcx+27h]
0x180007564  cmp     rax, rcx
0x180007567  jbe     loc_1800075F8
0x18000756d  mov     rcx, rax; Size
0x180007570  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007575  test    rax, rax
0x180007578  jnz     short loc_1800075AB
0x18000757a  lea     ecx, [rax+5]
0x18000757d  int     29h; Win8: RtlFailFast(ecx)
0x18000757f  mov     ecx, 0Ah
0x180007584  mov     rbp, rax
0x180007587  cmp     rax, rcx
0x18000758a  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007594  cmovb   rbp, rcx
0x180007598  lea     rcx, [rbp+1]
0x18000759c  cmp     rcx, rax
0x18000759f  ja      short loc_1800075F8
0x1800075a1  add     rcx, rcx
0x1800075a4  jnz     short loc_180007557
0x1800075a6  mov     rsi, r15
0x1800075a9  jmp     short loc_1800075C1
0x1800075ab  lea     rsi, [rax+27h]
0x1800075af  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1800075b3  mov     [rsi-8], rax
0x1800075b7  jmp     short loc_1800075C1
0x1800075b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800075be  mov     rsi, rax
0x1800075c1  mov     [rdi+10h], rbx
0x1800075c5  mov     rdx, r14; Src
0x1800075c8  add     rbx, rbx
0x1800075cb  mov     [rdi], rsi
0x1800075ce  mov     r8, rbx; Size
0x1800075d1  mov     [rdi+18h], rbp
0x1800075d5  mov     rcx, rsi; void *
0x1800075d8  call    memcpy_0
0x1800075dd  mov     [rbx+rsi], r15w
0x1800075e2  mov     rax, rdi
0x1800075e5  add     rsp, 28h
0x1800075e9  pop     r15
0x1800075eb  pop     r14
0x1800075ed  pop     rdi
0x1800075ee  pop     rsi
0x1800075ef  pop     rbp
0x1800075f0  pop     rbx
0x1800075f1  retn
0x1800075f2  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800075f8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
