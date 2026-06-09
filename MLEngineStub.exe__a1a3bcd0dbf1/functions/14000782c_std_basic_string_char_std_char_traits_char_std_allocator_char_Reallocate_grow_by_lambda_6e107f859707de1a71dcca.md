# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)

- ea: `0x14000782c`
- end: `0x14000799a`
- name: `??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z`
- size: `366`
- prototype: `void **__fastcall(void **Src, unsigned __int64, __int64, const void *, size_t Size)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140008058`
- `0x140009d9c`

## callees

- `0x1400023b4`
- `0x1400023ec`
- `0x14000782c`
- `0x14000a1a8`
- `0x14000a2ac`
- `0x14000ad14`

## pseudocode

```c
void **__fastcall std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        void **Src,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4,
        size_t Size)
{
  size_t v5; // r14
  __int64 v6; // rbx
  unsigned __int64 v9; // r12
  size_t v10; // rbp
  unsigned __int64 v11; // rcx
  size_t v12; // rcx
  void *v13; // rax
  _QWORD *v14; // rdi
  unsigned __int64 v15; // rdx
  char *v16; // r15
  _BYTE *v17; // rbx
  unsigned __int64 v18; // rdx
  _BYTE *v19; // rcx
  void **result; // rax

  v5 = (size_t)Src[2];
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  if ( 0x7FFFFFFFFFFFFFFFLL - v5 < a2 )
    std::_Xlen_string();
  v9 = (unsigned __int64)Src[3];
  v10 = v5 + a2;
  v11 = (v5 + a2) | 0xF;
  if ( v11 > 0x7FFFFFFFFFFFFFFFLL || (v15 = v9 >> 1, v9 > 0x7FFFFFFFFFFFFFFFLL - (v9 >> 1)) )
  {
    v12 = 0x8000000000000027uLL;
  }
  else
  {
    v6 = v11;
    if ( v11 < v9 + v15 )
      v6 = v9 + v15;
    if ( v6 == -1 )
    {
      v14 = 0;
      goto LABEL_15;
    }
    if ( (unsigned __int64)(v6 + 1) < 0x1000 )
    {
      v14 = operator new(v6 + 1);
      goto LABEL_15;
    }
    v12 = v6 + 40;
    if ( v6 + 40 < (unsigned __int64)(v6 + 1) )
      __scrt_throw_std_bad_array_new_length();
  }
  v13 = operator new(v12);
  if ( !v13 )
    goto LABEL_19;
  v14 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v14 - 1) = v13;
LABEL_15:
  Src[2] = (void *)v10;
  v16 = (char *)v14 + v5;
  Src[3] = (void *)v6;
  if ( v9 <= 0xF )
  {
    memcpy_0(v14, Src, v5);
    memcpy_0((char *)v14 + v5, a4, Size);
    v16[Size] = 0;
    goto LABEL_23;
  }
  v17 = *Src;
  memcpy_0(v14, *Src, v5);
  memcpy_0((char *)v14 + v5, a4, Size);
  v18 = v9 + 1;
  v16[Size] = 0;
  if ( v9 + 1 < 0x1000 )
  {
    v19 = v17;
    goto LABEL_21;
  }
  v19 = (_BYTE *)*((_QWORD *)v17 - 1);
  if ( (unsigned __int64)(v17 - v19 - 8) > 0x1F )
LABEL_19:
    __fastfail(5u);
  v18 = v9 + 40;
LABEL_21:
  operator delete(v19, v18);
LABEL_23:
  result = Src;
  *Src = v14;
  return result;
}

```

## disassembly

```asm
0x14000782c  push    rbx
0x14000782e  push    rbp
0x14000782f  push    rsi
0x140007830  push    rdi
0x140007831  push    r12
0x140007833  push    r13
0x140007835  push    r14
0x140007837  push    r15
0x140007839  sub     rsp, 28h
0x14000783d  mov     r14, [rcx+10h]
0x140007841  mov     rbx, 7FFFFFFFFFFFFFFFh
0x14000784b  mov     rax, rbx
0x14000784e  mov     r13, r9
0x140007851  sub     rax, r14
0x140007854  mov     rsi, rcx
0x140007857  cmp     rax, rdx
0x14000785a  jb      loc_14000798E
0x140007860  mov     r12, [rcx+18h]
0x140007864  lea     rbp, [r14+rdx]
0x140007868  mov     rcx, rbp
0x14000786b  or      rcx, 0Fh
0x14000786f  cmp     rcx, rbx
0x140007872  jbe     short loc_14000789A
0x140007874  mov     rcx, 8000000000000027h; Size
0x14000787e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007883  test    rax, rax
0x140007886  jz      loc_14000794B
0x14000788c  lea     rdi, [rax+27h]
0x140007890  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140007894  mov     [rdi-8], rax
0x140007898  jmp     short loc_1400078E8
0x14000789a  mov     rdx, r12
0x14000789d  mov     rax, rbx
0x1400078a0  shr     rdx, 1
0x1400078a3  sub     rax, rdx
0x1400078a6  cmp     r12, rax
0x1400078a9  ja      short loc_140007874
0x1400078ab  lea     rax, [r12+rdx]
0x1400078af  mov     rbx, rcx
0x1400078b2  cmp     rcx, rax
0x1400078b5  cmovb   rbx, rax
0x1400078b9  lea     rax, [rbx+1]
0x1400078bd  test    rax, rax
0x1400078c0  jnz     short loc_1400078C6
0x1400078c2  xor     edi, edi
0x1400078c4  jmp     short loc_1400078E8
0x1400078c6  cmp     rax, 1000h
0x1400078cc  jb      short loc_1400078DD
0x1400078ce  lea     rcx, [rax+27h]
0x1400078d2  cmp     rcx, rax
0x1400078d5  jbe     loc_140007994
0x1400078db  jmp     short loc_14000787E
0x1400078dd  mov     rcx, rax; Size
0x1400078e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400078e5  mov     rdi, rax
0x1400078e8  mov     [rsi+10h], rbp
0x1400078ec  lea     r15, [r14+rdi]
0x1400078f0  mov     rbp, [rsp+68h+Size]
0x1400078f8  mov     r8, r14; Size
0x1400078fb  mov     [rsi+18h], rbx
0x1400078ff  mov     rcx, rdi; void *
0x140007902  cmp     r12, 0Fh
0x140007906  jbe     short loc_14000795C
0x140007908  mov     rbx, [rsi]
0x14000790b  mov     rdx, rbx; Src
0x14000790e  call    memcpy_0
0x140007913  mov     r8, rbp; Size
0x140007916  mov     rdx, r13; Src
0x140007919  mov     rcx, r15; void *
0x14000791c  call    memcpy_0
0x140007921  lea     rdx, [r12+1]; unsigned __int64
0x140007926  mov     byte ptr [r15+rbp], 0
0x14000792b  cmp     rdx, 1000h
0x140007932  jb      short loc_140007952
0x140007934  mov     rcx, [rbx-8]
0x140007938  sub     rbx, rcx
0x14000793b  sub     rbx, 8
0x14000793f  cmp     rbx, 1Fh
0x140007943  ja      short loc_14000794B
0x140007945  add     rdx, 27h ; '''
0x140007949  jmp     short loc_140007955
0x14000794b  mov     ecx, 5
0x140007950  int     29h; Win8: RtlFailFast(ecx)
0x140007952  mov     rcx, rbx; void *
0x140007955  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000795a  jmp     short loc_140007977
0x14000795c  mov     rdx, rsi; Src
0x14000795f  call    memcpy_0
0x140007964  mov     r8, rbp; Size
0x140007967  mov     rdx, r13; Src
0x14000796a  mov     rcx, r15; void *
0x14000796d  call    memcpy_0
0x140007972  mov     byte ptr [r15+rbp], 0
0x140007977  mov     rax, rsi
0x14000797a  mov     [rax], rdi
0x14000797d  add     rsp, 28h
0x140007981  pop     r15
0x140007983  pop     r14
0x140007985  pop     r13
0x140007987  pop     r12
0x140007989  pop     rdi
0x14000798a  pop     rsi
0x14000798b  pop     rbp
0x14000798c  pop     rbx
0x14000798d  retn
0x14000798e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140007994  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
