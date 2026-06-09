# std::vector<char *,std::allocator<char *>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char *>>>,unsigned __int64,char * const &)

- ea: `0x1830b78b0`
- end: `0x1830b7b65`
- name: `?_Insert_n@?$vector@PEADV?$allocator@PEAD@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAD@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAD@std@@@std@@@2@_KAEBQEAD@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1830876d0`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x18306be50`
- `0x1830b78b0`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830b79b3`
- `VCRUNTIME140!memmove` at `0x1830b79d0`
- `VCRUNTIME140!memmove` at `0x1830b7a50`
- `VCRUNTIME140!memmove` at `0x1830b7ae8`
- `VCRUNTIME140!memmove` at `0x1830b7b0e`
- `VCRUNTIME140!memmove` at `0x1830b79b3`
- `VCRUNTIME140!memmove` at `0x1830b79d0`
- `VCRUNTIME140!memmove` at `0x1830b7a50`
- `VCRUNTIME140!memmove` at `0x1830b7ae8`
- `VCRUNTIME140!memmove` at `0x1830b7b0e`

## pseudocode

```c
_QWORD *__fastcall std::vector<char *>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        CxVector **a5)
{
  _BYTE *v9; // r8
  __int64 v10; // r12
  char *v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rsi
  __int64 v18; // r14
  unsigned __int64 v19; // rdi
  __int64 v20; // r14
  CxVector **v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  CxVector *v24; // rax
  CxVector *v25; // r15
  CxVector **v26; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-78h]
  char v30; // [rsp+20h] [rbp-78h]
  char v31; // [rsp+30h] [rbp-68h]
  CxVector *v32; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-58h]
  __int64 v34; // [rsp+48h] [rbp-50h]
  __int64 v35; // [rsp+50h] [rbp-48h]

  v35 = -2;
  v32 = a1;
  v9 = *(_BYTE **)a1;
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
  if ( a4 )
  {
    v11 = (char *)*((_QWORD *)a1 + 1);
    if ( (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v11) >> 3 >= a4 )
    {
      v20 = 8 * a4;
      if ( (v11 - a3) >> 3 >= a4 )
      {
        v25 = *a5;
        memmove(v11, &v11[-v20], 8 * a4);
        *((_QWORD *)a1 + 1) = &v11[v20];
        memmove(&a3[8 * a4], a3, (size_t)&v11[-8LL * a4 - (_QWORD)a3]);
        v26 = (CxVector **)a3;
        if ( a3 != &a3[v20] )
        {
          do
            *v26++ = v25;
          while ( v26 != (CxVector **)&a3[v20] );
        }
      }
      else
      {
        v32 = *a5;
        memmove(&a3[v20], a3, v11 - a3);
        try
        {
          v30 = v31;
          std::_Uninit_alloc_fill_n1<char * *,unsigned __int64,std::allocator<char *>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 3),
            &v32,
            a1,
            v30);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += v20;
        v21 = (CxVector **)a3;
        v22 = 0;
        v23 = (unsigned __int64)(*((_QWORD *)a1 + 1) - v20 - (_QWORD)a3 + 7) >> 3;
        if ( (unsigned __int64)a3 > *((_QWORD *)a1 + 1) - v20 )
          v23 = 0;
        if ( v23 )
        {
          v24 = v32;
          do
          {
            *v21++ = v24;
            ++v22;
          }
          while ( v22 != v23 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 3;
      if ( 0x1FFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v9) >> 3;
      v15 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v33 = v13;
      v16 = std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(
              a1,
              v13);
      v17 = (char *)v16;
      v34 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
      try
      {
        v29 = v31;
        std::_Uninit_alloc_fill_n1<char * *,unsigned __int64,std::allocator<char *>>(v16 + 8 * v18, a4, a5, a1, v29);
        memmove(v17, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[8 * a4 + 8 * v18], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v32);
        std::_Wrap_alloc<std::allocator<CxWrapper<CxVarDescriptor>>>::deallocate(Pointer, v34, v33);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<CxWrapper<CxComputation>>::deallocate(
          a1,
          *(_QWORD *)a1,
          (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 3);
      *((_QWORD *)a1 + 2) = &v17[8 * v13];
      *((_QWORD *)a1 + 1) = &v17[8 * v19];
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 8 * v10;
  return a2;
}

```

## disassembly

```asm
0x1830b78b0  mov     [rsp+Src], r8
0x1830b78b5  push    rbx
0x1830b78b6  push    rsi
0x1830b78b7  push    rdi
0x1830b78b8  push    r12
0x1830b78ba  push    r13
0x1830b78bc  push    r14
0x1830b78be  push    r15
0x1830b78c0  sub     rsp, 60h
0x1830b78c4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1830b78cd  mov     rdi, r9
0x1830b78d0  mov     rax, r8
0x1830b78d3  mov     r13, rdx
0x1830b78d6  mov     rbx, rcx
0x1830b78d9  mov     [rsp+98h+var_60], rcx
0x1830b78de  mov     r8, [rcx]
0x1830b78e1  mov     r12, rax
0x1830b78e4  sub     r12, r8
0x1830b78e7  sar     r12, 3
0x1830b78eb  test    r9, r9
0x1830b78ee  jz      loc_1830B7B47
0x1830b78f4  mov     rsi, [rcx+8]
0x1830b78f8  mov     rdx, [rcx+10h]
0x1830b78fc  mov     rcx, rdx
0x1830b78ff  sub     rcx, rsi
0x1830b7902  sar     rcx, 3
0x1830b7906  cmp     rcx, r9
0x1830b7909  jnb     loc_1830B7A18
0x1830b790f  sub     rsi, r8
0x1830b7912  sar     rsi, 3
0x1830b7916  mov     r9, 1FFFFFFFFFFFFFFFh
0x1830b7920  mov     rax, r9
0x1830b7923  sub     rax, rsi
0x1830b7926  cmp     rax, rdi
0x1830b7929  jnb     short loc_1830B7934
0x1830b792b  mov     rcx, rbx
0x1830b792e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1830b7934  lea     r15, [rdi+rsi]
0x1830b7938  sub     rdx, r8
0x1830b793b  sar     rdx, 3
0x1830b793f  mov     rax, rdx
0x1830b7942  shr     rax, 1
0x1830b7945  sub     r9, rax
0x1830b7948  add     rax, rdx
0x1830b794b  xor     ecx, ecx
0x1830b794d  cmp     r9, rdx
0x1830b7950  cmovnb  rcx, rax
0x1830b7954  cmp     rcx, r15
0x1830b7957  cmovnb  r15, rcx
0x1830b795b  mov     [rsp+98h+var_58], r15
0x1830b7960  mov     rdx, r15
0x1830b7963  mov     rcx, rbx
0x1830b7966  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1830b796b  mov     rsi, rax
0x1830b796e  mov     [rsp+98h+var_50], rax
0x1830b7973  mov     r14, [rsp+98h+Src]
0x1830b797b  sub     r14, [rbx]
0x1830b797e  sar     r14, 3
0x1830b7982  lea     rcx, [rax+r14*8]
0x1830b7986  movzx   eax, [rsp+98h+var_68]
0x1830b798b  mov     [rsp+98h+var_78], al
0x1830b798f  mov     r9, rbx
0x1830b7992  mov     r8, [rsp+98h+arg_20]
0x1830b799a  mov     rdx, rdi
0x1830b799d  call    ??$_Uninit_alloc_fill_n1@PEAPEAD_KV?$allocator@PEAD@std@@@std@@YAXPEAPEAD_KPEBQEADAEAU?$_Wrap_alloc@V?$allocator@PEAD@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<char * *,unsigned __int64,std::allocator<char *>>(char * *,unsigned __int64,char * const *,std::_Wrap_alloc<std::allocator<char *>> &,std::integral_constant<bool,0>)
0x1830b79a2  mov     rdx, [rbx]; Src
0x1830b79a5  mov     r8, [rsp+98h+Src]
0x1830b79ad  sub     r8, rdx; Size
0x1830b79b0  mov     rcx, rsi; void *
0x1830b79b3  call    cs:__imp_memmove
0x1830b79b9  mov     r8, [rbx+8]
0x1830b79bd  lea     rax, [rdi+r14]
0x1830b79c1  lea     rcx, [rsi+rax*8]; void *
0x1830b79c5  mov     rdx, [rsp+98h+Src]; Src
0x1830b79cd  sub     r8, rdx; Size
0x1830b79d0  call    cs:__imp_memmove
0x1830b79d6  nop
0x1830b79d7  mov     rdx, [rbx]
0x1830b79da  mov     rax, [rbx+8]
0x1830b79de  sub     rax, rdx
0x1830b79e1  sar     rax, 3
0x1830b79e5  add     rdi, rax
0x1830b79e8  test    rdx, rdx
0x1830b79eb  jz      short loc_1830B7A00
0x1830b79ed  mov     r8, [rbx+10h]
0x1830b79f1  sub     r8, rdx
0x1830b79f4  sar     r8, 3
0x1830b79f8  mov     rcx, rbx
0x1830b79fb  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1830b7a00  lea     rax, [rsi+r15*8]
0x1830b7a04  mov     [rbx+10h], rax
0x1830b7a08  lea     rax, [rsi+rdi*8]
0x1830b7a0c  mov     [rbx+8], rax
0x1830b7a10  mov     [rbx], rsi
0x1830b7a13  jmp     loc_1830B7B47
0x1830b7a18  mov     rcx, rsi
0x1830b7a1b  sub     rcx, rax
0x1830b7a1e  sar     rcx, 3
0x1830b7a22  lea     r14, ds:0[r9*8]
0x1830b7a2a  cmp     rcx, rdi
0x1830b7a2d  jnb     loc_1830B7AD1
0x1830b7a33  mov     rcx, [rsp+98h+arg_20]
0x1830b7a3b  mov     rdx, [rcx]
0x1830b7a3e  mov     [rsp+98h+var_60], rdx
0x1830b7a43  lea     rcx, [r14+rax]; void *
0x1830b7a47  sub     rsi, rax
0x1830b7a4a  mov     r8, rsi; Size
0x1830b7a4d  mov     rdx, rax; Src
0x1830b7a50  call    cs:__imp_memmove
0x1830b7a56  nop
0x1830b7a57  mov     rax, [rbx+8]
0x1830b7a5b  sub     rax, [rsp+98h+Src]
0x1830b7a63  sar     rax, 3
0x1830b7a67  sub     rdi, rax
0x1830b7a6a  movzx   eax, [rsp+98h+var_68]
0x1830b7a6f  mov     [rsp+98h+var_78], al
0x1830b7a73  mov     r9, rbx
0x1830b7a76  lea     r8, [rsp+98h+var_60]
0x1830b7a7b  mov     rdx, rdi
0x1830b7a7e  mov     rcx, [rbx+8]
0x1830b7a82  call    ??$_Uninit_alloc_fill_n1@PEAPEAD_KV?$allocator@PEAD@std@@@std@@YAXPEAPEAD_KPEBQEADAEAU?$_Wrap_alloc@V?$allocator@PEAD@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<char * *,unsigned __int64,std::allocator<char *>>(char * *,unsigned __int64,char * const *,std::_Wrap_alloc<std::allocator<char *>> &,std::integral_constant<bool,0>)
0x1830b7a87  nop
0x1830b7a88  add     [rbx+8], r14
0x1830b7a8c  mov     rax, [rbx+8]
0x1830b7a90  sub     rax, r14
0x1830b7a93  mov     rdx, [rsp+98h+Src]
0x1830b7a9b  xor     ecx, ecx
0x1830b7a9d  mov     r8, rax
0x1830b7aa0  sub     r8, rdx
0x1830b7aa3  add     r8, 7
0x1830b7aa7  shr     r8, 3
0x1830b7aab  cmp     rdx, rax
0x1830b7aae  cmova   r8, rcx
0x1830b7ab2  test    r8, r8
0x1830b7ab5  jz      loc_1830B7B47
0x1830b7abb  mov     rax, [rsp+98h+var_60]
0x1830b7ac0  mov     [rdx], rax
0x1830b7ac3  lea     rdx, [rdx+8]
0x1830b7ac7  inc     rcx
0x1830b7aca  cmp     rcx, r8
0x1830b7acd  jnz     short loc_1830B7AC0
0x1830b7acf  jmp     short loc_1830B7B47
0x1830b7ad1  mov     rax, [rsp+98h+arg_20]
0x1830b7ad9  mov     r15, [rax]
0x1830b7adc  mov     rdx, rsi
0x1830b7adf  sub     rdx, r14; Src
0x1830b7ae2  mov     r8, r14; Size
0x1830b7ae5  mov     rcx, rsi; void *
0x1830b7ae8  call    cs:__imp_memmove
0x1830b7aee  lea     rax, [r14+rsi]
0x1830b7af2  mov     [rbx+8], rax
0x1830b7af6  imul    r8, rdi, -8
0x1830b7afa  mov     rdx, [rsp+98h+Src]; Src
0x1830b7b02  sub     r8, rdx
0x1830b7b05  add     r8, rsi; Size
0x1830b7b08  sub     rsi, r8
0x1830b7b0b  mov     rcx, rsi; void *
0x1830b7b0e  call    cs:__imp_memmove
0x1830b7b14  mov     r8, [rsp+98h+Src]
0x1830b7b1c  lea     rax, [r14+r8]
0x1830b7b20  cmp     r8, rax
0x1830b7b23  jz      short loc_1830B7B47
0x1830b7b25  nop     word ptr [rax+rax+00000000h]
0x1830b7b30  mov     [r8], r15
0x1830b7b33  add     r8, 8
0x1830b7b37  mov     rdx, [rsp+98h+Src]
0x1830b7b3f  add     rdx, r14
0x1830b7b42  cmp     r8, rdx
0x1830b7b45  jnz     short loc_1830B7B30
0x1830b7b47  mov     rcx, [rbx]
0x1830b7b4a  lea     rdx, [rcx+r12*8]
0x1830b7b4e  mov     [r13+0], rdx
0x1830b7b52  mov     rax, r13
0x1830b7b55  add     rsp, 60h
0x1830b7b59  pop     r15
0x1830b7b5b  pop     r14
0x1830b7b5d  pop     r13
0x1830b7b5f  pop     r12
0x1830b7b61  pop     rdi
0x1830b7b62  pop     rsi
0x1830b7b63  pop     rbx
0x1830b7b64  retn
```
