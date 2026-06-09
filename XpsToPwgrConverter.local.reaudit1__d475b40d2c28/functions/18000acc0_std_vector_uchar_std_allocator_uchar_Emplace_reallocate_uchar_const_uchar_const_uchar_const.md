# std::vector<uchar,std::allocator<uchar>>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)

- ea: `0x18000acc0`
- end: `0x18000ae26`
- name: `??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z`
- size: `358`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000b238`
- `0x18000b498`
- `0x18000b74c`
- `0x18000ba80`
- `0x18000bd40`
- `0x18000c078`

## callees

- `0x180001b30`
- `0x18000200c`
- `0x18000acc0`
- `0x18000c968`
- `0x18000c990`
- `0x18000f55c`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(
        _QWORD *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  _BYTE *v3; // rbp
  size_t v4; // rbx
  __int64 v6; // rax
  unsigned __int64 v9; // r12
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  size_t v12; // rcx
  void *v13; // rax
  _QWORD *v14; // rdi
  _BYTE *v15; // r14
  void *v16; // rcx
  _BYTE *v17; // r8
  _BYTE *v18; // rdx
  size_t v19; // r8
  _BYTE *v20; // rax
  _BYTE *v21; // rcx
  char *result; // rax

  v3 = (_BYTE *)*a1;
  v4 = 0x7FFFFFFFFFFFFFFFLL;
  v6 = a1[1] - *a1;
  if ( v6 == 0x7FFFFFFFFFFFFFFFLL )
    std::vector<unsigned char>::_Xlength();
  v9 = v6 + 1;
  v10 = a1[2] - (_QWORD)v3;
  v11 = v10 >> 1;
  if ( v10 <= 0x7FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v4 = v6 + 1;
    if ( v10 + v11 >= v9 )
      v4 = v10 + v11;
    if ( !v4 )
    {
      v14 = 0;
      goto LABEL_14;
    }
    if ( v4 < 0x1000 )
    {
      v14 = operator new(v4);
      goto LABEL_14;
    }
    v12 = v4 + 39;
    if ( v4 + 39 < v4 )
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v12 = 0x8000000000000026uLL;
  }
  v13 = operator new(v12);
  if ( !v13 )
    goto LABEL_20;
  v14 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v14 - 1) = v13;
LABEL_14:
  v15 = (char *)v14 + a2 - v3;
  *v15 = *a3;
  v16 = v14;
  v17 = (_BYTE *)a1[1];
  v18 = (_BYTE *)*a1;
  if ( a2 == v17 )
  {
    v19 = v17 - v18;
  }
  else
  {
    memmove_0(v14, v18, (size_t)&a2[-*a1]);
    v16 = v15 + 1;
    v19 = a1[1] - (_QWORD)a2;
    v18 = a2;
  }
  memmove_0(v16, v18, v19);
  v20 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( a1[2] - (_QWORD)v20 < 0x1000u )
    {
      v21 = (_BYTE *)*a1;
    }
    else
    {
      v21 = (_BYTE *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v20 - v21 - 8) > 0x1F )
LABEL_20:
        __fastfail(5u);
    }
    operator delete(v21);
  }
  *a1 = v14;
  a1[1] = (char *)v14 + v9;
  result = (char *)v14 + a2 - v3;
  a1[2] = (char *)v14 + v4;
  return result;
}

```

## disassembly

```asm
0x18000acc0  push    rbx
0x18000acc2  push    rbp
0x18000acc3  push    rsi
0x18000acc4  push    rdi
0x18000acc5  push    r12
0x18000acc7  push    r13
0x18000acc9  push    r14
0x18000accb  push    r15
0x18000accd  sub     rsp, 28h
0x18000acd1  mov     rbp, [rcx]
0x18000acd4  mov     rbx, 7FFFFFFFFFFFFFFFh
0x18000acde  mov     rax, [rcx+8]
0x18000ace2  mov     r13, r8
0x18000ace5  sub     rax, rbp
0x18000ace8  mov     r15, rdx
0x18000aceb  mov     rsi, rcx
0x18000acee  cmp     rax, rbx
0x18000acf1  jz      loc_18000AE1A
0x18000acf7  mov     rcx, [rcx+10h]
0x18000acfb  lea     r12, [rax+1]
0x18000acff  sub     rcx, rbp
0x18000ad02  mov     rax, rbx
0x18000ad05  mov     rdx, rcx
0x18000ad08  shr     rdx, 1
0x18000ad0b  sub     rax, rdx
0x18000ad0e  cmp     rcx, rax
0x18000ad11  jbe     short loc_18000AD39
0x18000ad13  mov     rcx, 8000000000000026h; Size
0x18000ad1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad22  test    rax, rax
0x18000ad25  jz      loc_18000ADE4
0x18000ad2b  lea     rdi, [rax+27h]
0x18000ad2f  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000ad33  mov     [rdi-8], rax
0x18000ad37  jmp     short loc_18000AD73
0x18000ad39  lea     rax, [rcx+rdx]
0x18000ad3d  mov     rbx, r12
0x18000ad40  cmp     rax, r12
0x18000ad43  cmovnb  rbx, rax
0x18000ad47  test    rbx, rbx
0x18000ad4a  jnz     short loc_18000AD50
0x18000ad4c  xor     edi, edi
0x18000ad4e  jmp     short loc_18000AD73
0x18000ad50  cmp     rbx, 1000h
0x18000ad57  jb      short loc_18000AD68
0x18000ad59  lea     rcx, [rbx+27h]
0x18000ad5d  cmp     rcx, rbx
0x18000ad60  jbe     loc_18000AE20
0x18000ad66  jmp     short loc_18000AD1D
0x18000ad68  mov     rcx, rbx; Size
0x18000ad6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad70  mov     rdi, rax
0x18000ad73  mov     cl, [r13+0]
0x18000ad77  mov     r14, r15
0x18000ad7a  sub     r14, rbp
0x18000ad7d  add     r14, rdi
0x18000ad80  mov     [r14], cl
0x18000ad83  mov     rcx, rdi; void *
0x18000ad86  mov     r8, [rsi+8]
0x18000ad8a  mov     rdx, [rsi]; Src
0x18000ad8d  cmp     r15, r8
0x18000ad90  jnz     short loc_18000AD97
0x18000ad92  sub     r8, rdx
0x18000ad95  jmp     short loc_18000ADB0
0x18000ad97  mov     r8, r15
0x18000ad9a  sub     r8, [rsi]; Size
0x18000ad9d  call    memmove_0
0x18000ada2  mov     r8, [rsi+8]
0x18000ada6  lea     rcx, [r14+1]; void *
0x18000adaa  sub     r8, r15; Size
0x18000adad  mov     rdx, r15; Src
0x18000adb0  call    memmove_0
0x18000adb5  mov     rax, [rsi]
0x18000adb8  test    rax, rax
0x18000adbb  jz      short loc_18000ADF3
0x18000adbd  mov     rdx, [rsi+10h]
0x18000adc1  sub     rdx, rax; unsigned __int64
0x18000adc4  cmp     rdx, 1000h
0x18000adcb  jb      short loc_18000ADEB
0x18000adcd  mov     rcx, [rax-8]
0x18000add1  sub     rax, rcx
0x18000add4  sub     rax, 8
0x18000add8  cmp     rax, 1Fh
0x18000addc  ja      short loc_18000ADE4
0x18000adde  add     rdx, 27h ; '''
0x18000ade2  jmp     short loc_18000ADEE
0x18000ade4  mov     ecx, 5
0x18000ade9  int     29h; Win8: RtlFailFast(ecx)
0x18000adeb  mov     rcx, rax; void *
0x18000adee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000adf3  lea     rcx, [r12+rdi]
0x18000adf7  mov     [rsi], rdi
0x18000adfa  mov     [rsi+8], rcx
0x18000adfe  mov     rax, r14
0x18000ae01  lea     rcx, [rdi+rbx]
0x18000ae05  mov     [rsi+10h], rcx
0x18000ae09  add     rsp, 28h
0x18000ae0d  pop     r15
0x18000ae0f  pop     r14
0x18000ae11  pop     r13
0x18000ae13  pop     r12
0x18000ae15  pop     rdi
0x18000ae16  pop     rsi
0x18000ae17  pop     rbp
0x18000ae18  pop     rbx
0x18000ae19  retn
0x18000ae1a  call    ?_Xlength@?$vector@EV?$allocator@E@std@@@std@@CAXXZ; std::vector<uchar>::_Xlength(void)
0x18000ae20  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
