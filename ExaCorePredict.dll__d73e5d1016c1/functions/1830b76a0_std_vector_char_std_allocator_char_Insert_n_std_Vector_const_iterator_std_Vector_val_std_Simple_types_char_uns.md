# std::vector<char,std::allocator<char>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,unsigned __int64,char const &)

- ea: `0x1830b76a0`
- end: `0x1830b78aa`
- name: `?_Insert_n@?$vector@DV?$allocator@D@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@2@_KAEBD@Z`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x183086e70`

## callees

- `0x1815cc2e0`
- `0x182da9c80`
- `0x183066770`
- `0x1830b76a0`
- `0x1832dbeb0`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830b7789`
- `VCRUNTIME140!memmove` at `0x1830b77a5`
- `VCRUNTIME140!memmove` at `0x1830b7801`
- `VCRUNTIME140!memmove` at `0x1830b7853`
- `VCRUNTIME140!memmove` at `0x1830b7875`
- `VCRUNTIME140!memmove` at `0x1830b7789`
- `VCRUNTIME140!memmove` at `0x1830b77a5`
- `VCRUNTIME140!memmove` at `0x1830b7801`
- `VCRUNTIME140!memmove` at `0x1830b7853`
- `VCRUNTIME140!memmove` at `0x1830b7875`

## pseudocode

```c
_QWORD *__fastcall std::vector<char>::_Insert_n(CxVector *a1, _QWORD *a2, _BYTE *a3, size_t a4, _BYTE *a5)
{
  _BYTE *v8; // rcx
  signed __int64 v9; // r12
  __int64 v10; // r15
  __int64 v11; // r15
  size_t v12; // rdi
  unsigned __int64 v13; // r8
  size_t v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  char *v17; // r15
  size_t v18; // r14
  int v19; // ebx
  void *v20; // rcx
  size_t v21; // r8
  int v22; // edx
  int v23; // edi
  struct CxVector *Pointer; // rax
  __int64 v27; // [rsp+38h] [rbp-50h]

  v8 = *(_BYTE **)a1;
  v9 = a3 - v8;
  if ( a4 )
  {
    v10 = *((_QWORD *)a1 + 1);
    if ( *((_QWORD *)a1 + 2) - v10 >= a4 )
    {
      if ( v10 - (__int64)a3 >= a4 )
      {
        v23 = (char)*a5;
        memmove(*((void **)a1 + 1), (const void *)(v10 - a4), a4);
        *((_QWORD *)a1 + 1) = a4 + v10;
        memmove(&a3[a4], a3, v10 - a4 - (_QWORD)a3);
        v22 = v23;
        v21 = a4;
        v20 = a3;
      }
      else
      {
        LOBYTE(v19) = *a5;
        memmove(&a3[a4], a3, v10 - (_QWORD)a3);
        try
        {
          v19 = (char)v19;
          memset_0(*((void **)a1 + 1), (char)v19, (size_t)&a3[a4 - *((_QWORD *)a1 + 1)]);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += a4;
        v20 = a3;
        v21 = *((_QWORD *)a1 + 1) - a4 - (_QWORD)a3;
        v22 = v19;
      }
      memset_0(v20, v22, v21);
    }
    else
    {
      v11 = v10 - (_QWORD)v8;
      if ( ~v11 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v12 = a4 + v11;
      v13 = *((_QWORD *)a1 + 2) - (_QWORD)v8;
      v14 = 0;
      if ( ~(v13 >> 1) >= v13 )
        v14 = v13 + (v13 >> 1);
      if ( v14 >= v12 )
        v12 = v14;
      v15 = std::_Wrap_alloc<std::allocator<unsigned char>>::allocate(a1, v12);
      v16 = v15;
      v27 = v15;
      v17 = &a3[-*(_QWORD *)a1];
      try
      {
        memset_0(&v17[v15], (char)*a5, a4);
        memmove((void *)v16, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[a4 + v16], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(a1);
        std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(Pointer, v27, v12);
        throw;
      }
      v18 = *((_QWORD *)a1 + 1) - *(_QWORD *)a1 + a4;
      if ( *(_QWORD *)a1 )
        std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(
          a1,
          *(_QWORD *)a1,
          *((_QWORD *)a1 + 2) - *(_QWORD *)a1);
      *((_QWORD *)a1 + 2) = v16 + v12;
      *((_QWORD *)a1 + 1) = v18 + v16;
      *(_QWORD *)a1 = v16;
    }
  }
  *a2 = v9 + *(_QWORD *)a1;
  return a2;
}

```

## disassembly

```asm
0x1830b76a0  mov     [rsp+Src], r8
0x1830b76a5  push    rbx
0x1830b76a6  push    rsi
0x1830b76a7  push    rdi
0x1830b76a8  push    r12
0x1830b76aa  push    r13
0x1830b76ac  push    r14
0x1830b76ae  push    r15
0x1830b76b0  sub     rsp, 50h
0x1830b76b4  mov     [rsp+88h+var_48], 0FFFFFFFFFFFFFFFEh
0x1830b76bd  mov     r14, r9
0x1830b76c0  mov     rax, r8
0x1830b76c3  mov     r13, rdx
0x1830b76c6  mov     rsi, rcx
0x1830b76c9  mov     [rsp+88h+var_60], rcx
0x1830b76ce  mov     r9, [rsp+88h+arg_20]
0x1830b76d6  mov     [rsp+88h+var_68], r9
0x1830b76db  mov     rcx, [rcx]
0x1830b76de  mov     r12, r8
0x1830b76e1  sub     r12, rcx
0x1830b76e4  test    r14, r14
0x1830b76e7  jz      loc_1830B788D
0x1830b76ed  mov     r8, [rsi+10h]
0x1830b76f1  mov     r15, [rsi+8]
0x1830b76f5  mov     rdx, r8
0x1830b76f8  sub     rdx, r15
0x1830b76fb  cmp     rdx, r14
0x1830b76fe  jnb     loc_1830B77E5
0x1830b7704  sub     r15, rcx
0x1830b7707  mov     rax, r15
0x1830b770a  not     rax
0x1830b770d  cmp     rax, r14
0x1830b7710  jnb     short loc_1830B771B
0x1830b7712  mov     rcx, rsi
0x1830b7715  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1830b771b  lea     rdi, [r14+r15]
0x1830b771f  sub     r8, rcx
0x1830b7722  mov     rax, r8
0x1830b7725  shr     rax, 1
0x1830b7728  mov     rcx, rax
0x1830b772b  not     rcx
0x1830b772e  add     rax, r8
0x1830b7731  xor     edx, edx
0x1830b7733  cmp     rcx, r8
0x1830b7736  cmovnb  rdx, rax
0x1830b773a  cmp     rdx, rdi
0x1830b773d  cmovnb  rdi, rdx
0x1830b7741  mov     [rsp+88h+var_58], rdi
0x1830b7746  mov     rdx, rdi
0x1830b7749  mov     rcx, rsi
0x1830b774c  call    ?allocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::allocate(unsigned __int64)
0x1830b7751  mov     rbx, rax
0x1830b7754  mov     [rsp+88h+var_50], rax
0x1830b7759  mov     r15, [rsp+88h+Src]
0x1830b7761  sub     r15, [rsi]
0x1830b7764  lea     rcx, [r15+rax]; void *
0x1830b7768  mov     rax, [rsp+88h+var_68]
0x1830b776d  movsx   edx, byte ptr [rax]; Val
0x1830b7770  mov     r8, r14; Size
0x1830b7773  call    memset_0
0x1830b7778  mov     rdx, [rsi]; Src
0x1830b777b  mov     r8, [rsp+88h+Src]
0x1830b7783  sub     r8, rdx; Size
0x1830b7786  mov     rcx, rbx; void *
0x1830b7789  call    cs:__imp_memmove
0x1830b778f  mov     r8, [rsi+8]
0x1830b7793  lea     rcx, [r14+r15]
0x1830b7797  add     rcx, rbx; void *
0x1830b779a  mov     rdx, [rsp+88h+Src]; Src
0x1830b77a2  sub     r8, rdx; Size
0x1830b77a5  call    cs:__imp_memmove
0x1830b77ab  nop
0x1830b77ac  mov     rdx, [rsi]
0x1830b77af  mov     rax, [rsi+8]
0x1830b77b3  sub     rax, rdx
0x1830b77b6  add     r14, rax
0x1830b77b9  test    rdx, rdx
0x1830b77bc  jz      short loc_1830B77CD
0x1830b77be  mov     r8, [rsi+10h]
0x1830b77c2  sub     r8, rdx
0x1830b77c5  mov     rcx, rsi
0x1830b77c8  call    ?deallocate@?$_Wrap_alloc@V?$allocator@E@std@@@std@@QEAAXPEAE_K@Z; std::_Wrap_alloc<std::allocator<uchar>>::deallocate(uchar *,unsigned __int64)
0x1830b77cd  lea     rax, [rbx+rdi]
0x1830b77d1  mov     [rsi+10h], rax
0x1830b77d5  lea     rax, [r14+rbx]
0x1830b77d9  mov     [rsi+8], rax
0x1830b77dd  mov     [rsi], rbx
0x1830b77e0  jmp     loc_1830B788D
0x1830b77e5  mov     rcx, r15
0x1830b77e8  sub     rcx, rax
0x1830b77eb  cmp     rcx, r14
0x1830b77ee  jnb     short loc_1830B7840
0x1830b77f0  movzx   ebx, byte ptr [r9]
0x1830b77f4  lea     rcx, [r14+rax]; void *
0x1830b77f8  sub     r15, rax
0x1830b77fb  mov     r8, r15; Size
0x1830b77fe  mov     rdx, rax; Src
0x1830b7801  call    cs:__imp_memmove
0x1830b7807  nop
0x1830b7808  mov     r8, r14
0x1830b780b  sub     r8, [rsi+8]
0x1830b780f  add     r8, [rsp+88h+Src]; Size
0x1830b7817  movsx   ebx, bl
0x1830b781a  mov     edx, ebx; Val
0x1830b781c  mov     rcx, [rsi+8]; void *
0x1830b7820  call    memset_0
0x1830b7825  nop
0x1830b7826  add     [rsi+8], r14
0x1830b782a  mov     r8, [rsi+8]
0x1830b782e  sub     r8, r14
0x1830b7831  mov     rcx, [rsp+88h+Src]
0x1830b7839  sub     r8, rcx
0x1830b783c  mov     edx, ebx
0x1830b783e  jmp     short loc_1830B7888
0x1830b7840  movsx   edi, byte ptr [r9]
0x1830b7844  mov     rbx, r15
0x1830b7847  sub     rbx, r14
0x1830b784a  mov     r8, r14; Size
0x1830b784d  mov     rdx, rbx; Src
0x1830b7850  mov     rcx, r15; void *
0x1830b7853  call    cs:__imp_memmove
0x1830b7859  lea     rax, [r14+r15]
0x1830b785d  mov     [rsi+8], rax
0x1830b7861  mov     rdx, [rsp+88h+Src]; Src
0x1830b7869  sub     rbx, rdx
0x1830b786c  sub     r15, rbx
0x1830b786f  mov     r8, rbx; Size
0x1830b7872  mov     rcx, r15; void *
0x1830b7875  call    cs:__imp_memmove
0x1830b787b  mov     edx, edi; Val
0x1830b787d  mov     r8, r14; Size
0x1830b7880  mov     rcx, [rsp+88h+Src]; void *
0x1830b7888  call    memset_0
0x1830b788d  mov     rdx, [rsi]
0x1830b7890  add     rdx, r12
0x1830b7893  mov     [r13+0], rdx
0x1830b7897  mov     rax, r13
0x1830b789a  add     rsp, 50h
0x1830b789e  pop     r15
0x1830b78a0  pop     r14
0x1830b78a2  pop     r13
0x1830b78a4  pop     r12
0x1830b78a6  pop     rdi
0x1830b78a7  pop     rsi
0x1830b78a8  pop     rbx
0x1830b78a9  retn
```
