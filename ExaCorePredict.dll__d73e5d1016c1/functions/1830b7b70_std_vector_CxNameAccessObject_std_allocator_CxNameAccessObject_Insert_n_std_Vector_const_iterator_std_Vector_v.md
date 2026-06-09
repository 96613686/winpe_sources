# std::vector<CxNameAccessObject *,std::allocator<CxNameAccessObject *>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CxNameAccessObject *>>>,unsigned __int64,CxNameAccessObject * const &)

- ea: `0x1830b7b70`
- end: `0x1830b7e25`
- name: `?_Insert_n@?$vector@PEAVCxNameAccessObject@@V?$allocator@PEAVCxNameAccessObject@@@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCxNameAccessObject@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCxNameAccessObject@@@std@@@std@@@2@_KAEBQEAVCxNameAccessObject@@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1830877e0`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x18306be80`
- `0x1830b7b70`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830b7c73`
- `VCRUNTIME140!memmove` at `0x1830b7c90`
- `VCRUNTIME140!memmove` at `0x1830b7d10`
- `VCRUNTIME140!memmove` at `0x1830b7da8`
- `VCRUNTIME140!memmove` at `0x1830b7dce`
- `VCRUNTIME140!memmove` at `0x1830b7c73`
- `VCRUNTIME140!memmove` at `0x1830b7c90`
- `VCRUNTIME140!memmove` at `0x1830b7d10`
- `VCRUNTIME140!memmove` at `0x1830b7da8`
- `VCRUNTIME140!memmove` at `0x1830b7dce`

## pseudocode

```c
_QWORD *__fastcall std::vector<CxNameAccessObject *>::_Insert_n(
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
          std::_Uninit_alloc_fill_n1<CxNameAccessObject * *,unsigned __int64,std::allocator<CxNameAccessObject *>>(
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
        std::_Uninit_alloc_fill_n1<CxNameAccessObject * *,unsigned __int64,std::allocator<CxNameAccessObject *>>(
          v16 + 8 * v18,
          a4,
          a5,
          a1,
          v29);
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
0x1830b7b70  mov     [rsp+Src], r8
0x1830b7b75  push    rbx
0x1830b7b76  push    rsi
0x1830b7b77  push    rdi
0x1830b7b78  push    r12
0x1830b7b7a  push    r13
0x1830b7b7c  push    r14
0x1830b7b7e  push    r15
0x1830b7b80  sub     rsp, 60h
0x1830b7b84  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1830b7b8d  mov     rdi, r9
0x1830b7b90  mov     rax, r8
0x1830b7b93  mov     r13, rdx
0x1830b7b96  mov     rbx, rcx
0x1830b7b99  mov     [rsp+98h+var_60], rcx
0x1830b7b9e  mov     r8, [rcx]
0x1830b7ba1  mov     r12, rax
0x1830b7ba4  sub     r12, r8
0x1830b7ba7  sar     r12, 3
0x1830b7bab  test    r9, r9
0x1830b7bae  jz      loc_1830B7E07
0x1830b7bb4  mov     rsi, [rcx+8]
0x1830b7bb8  mov     rdx, [rcx+10h]
0x1830b7bbc  mov     rcx, rdx
0x1830b7bbf  sub     rcx, rsi
0x1830b7bc2  sar     rcx, 3
0x1830b7bc6  cmp     rcx, r9
0x1830b7bc9  jnb     loc_1830B7CD8
0x1830b7bcf  sub     rsi, r8
0x1830b7bd2  sar     rsi, 3
0x1830b7bd6  mov     r9, 1FFFFFFFFFFFFFFFh
0x1830b7be0  mov     rax, r9
0x1830b7be3  sub     rax, rsi
0x1830b7be6  cmp     rax, rdi
0x1830b7be9  jnb     short loc_1830B7BF4
0x1830b7beb  mov     rcx, rbx
0x1830b7bee  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1830b7bf4  lea     r15, [rdi+rsi]
0x1830b7bf8  sub     rdx, r8
0x1830b7bfb  sar     rdx, 3
0x1830b7bff  mov     rax, rdx
0x1830b7c02  shr     rax, 1
0x1830b7c05  sub     r9, rax
0x1830b7c08  add     rax, rdx
0x1830b7c0b  xor     ecx, ecx
0x1830b7c0d  cmp     r9, rdx
0x1830b7c10  cmovnb  rcx, rax
0x1830b7c14  cmp     rcx, r15
0x1830b7c17  cmovnb  r15, rcx
0x1830b7c1b  mov     [rsp+98h+var_58], r15
0x1830b7c20  mov     rdx, r15
0x1830b7c23  mov     rcx, rbx
0x1830b7c26  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1830b7c2b  mov     rsi, rax
0x1830b7c2e  mov     [rsp+98h+var_50], rax
0x1830b7c33  mov     r14, [rsp+98h+Src]
0x1830b7c3b  sub     r14, [rbx]
0x1830b7c3e  sar     r14, 3
0x1830b7c42  lea     rcx, [rax+r14*8]
0x1830b7c46  movzx   eax, [rsp+98h+var_68]
0x1830b7c4b  mov     [rsp+98h+var_78], al
0x1830b7c4f  mov     r9, rbx
0x1830b7c52  mov     r8, [rsp+98h+arg_20]
0x1830b7c5a  mov     rdx, rdi
0x1830b7c5d  call    ??$_Uninit_alloc_fill_n1@PEAPEAVCxNameAccessObject@@_KV?$allocator@PEAVCxNameAccessObject@@@std@@@std@@YAXPEAPEAVCxNameAccessObject@@_KPEBQEAV1@AEAU?$_Wrap_alloc@V?$allocator@PEAVCxNameAccessObject@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<CxNameAccessObject * *,unsigned __int64,std::allocator<CxNameAccessObject *>>(CxNameAccessObject * *,unsigned __int64,CxNameAccessObject * const *,std::_Wrap_alloc<std::allocator<CxNameAccessObject *>> &,std::integral_constant<bool,0>)
0x1830b7c62  mov     rdx, [rbx]; Src
0x1830b7c65  mov     r8, [rsp+98h+Src]
0x1830b7c6d  sub     r8, rdx; Size
0x1830b7c70  mov     rcx, rsi; void *
0x1830b7c73  call    cs:__imp_memmove
0x1830b7c79  mov     r8, [rbx+8]
0x1830b7c7d  lea     rax, [rdi+r14]
0x1830b7c81  lea     rcx, [rsi+rax*8]; void *
0x1830b7c85  mov     rdx, [rsp+98h+Src]; Src
0x1830b7c8d  sub     r8, rdx; Size
0x1830b7c90  call    cs:__imp_memmove
0x1830b7c96  nop
0x1830b7c97  mov     rdx, [rbx]
0x1830b7c9a  mov     rax, [rbx+8]
0x1830b7c9e  sub     rax, rdx
0x1830b7ca1  sar     rax, 3
0x1830b7ca5  add     rdi, rax
0x1830b7ca8  test    rdx, rdx
0x1830b7cab  jz      short loc_1830B7CC0
0x1830b7cad  mov     r8, [rbx+10h]
0x1830b7cb1  sub     r8, rdx
0x1830b7cb4  sar     r8, 3
0x1830b7cb8  mov     rcx, rbx
0x1830b7cbb  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1830b7cc0  lea     rax, [rsi+r15*8]
0x1830b7cc4  mov     [rbx+10h], rax
0x1830b7cc8  lea     rax, [rsi+rdi*8]
0x1830b7ccc  mov     [rbx+8], rax
0x1830b7cd0  mov     [rbx], rsi
0x1830b7cd3  jmp     loc_1830B7E07
0x1830b7cd8  mov     rcx, rsi
0x1830b7cdb  sub     rcx, rax
0x1830b7cde  sar     rcx, 3
0x1830b7ce2  lea     r14, ds:0[r9*8]
0x1830b7cea  cmp     rcx, rdi
0x1830b7ced  jnb     loc_1830B7D91
0x1830b7cf3  mov     rcx, [rsp+98h+arg_20]
0x1830b7cfb  mov     rdx, [rcx]
0x1830b7cfe  mov     [rsp+98h+var_60], rdx
0x1830b7d03  lea     rcx, [r14+rax]; void *
0x1830b7d07  sub     rsi, rax
0x1830b7d0a  mov     r8, rsi; Size
0x1830b7d0d  mov     rdx, rax; Src
0x1830b7d10  call    cs:__imp_memmove
0x1830b7d16  nop
0x1830b7d17  mov     rax, [rbx+8]
0x1830b7d1b  sub     rax, [rsp+98h+Src]
0x1830b7d23  sar     rax, 3
0x1830b7d27  sub     rdi, rax
0x1830b7d2a  movzx   eax, [rsp+98h+var_68]
0x1830b7d2f  mov     [rsp+98h+var_78], al
0x1830b7d33  mov     r9, rbx
0x1830b7d36  lea     r8, [rsp+98h+var_60]
0x1830b7d3b  mov     rdx, rdi
0x1830b7d3e  mov     rcx, [rbx+8]
0x1830b7d42  call    ??$_Uninit_alloc_fill_n1@PEAPEAVCxNameAccessObject@@_KV?$allocator@PEAVCxNameAccessObject@@@std@@@std@@YAXPEAPEAVCxNameAccessObject@@_KPEBQEAV1@AEAU?$_Wrap_alloc@V?$allocator@PEAVCxNameAccessObject@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<CxNameAccessObject * *,unsigned __int64,std::allocator<CxNameAccessObject *>>(CxNameAccessObject * *,unsigned __int64,CxNameAccessObject * const *,std::_Wrap_alloc<std::allocator<CxNameAccessObject *>> &,std::integral_constant<bool,0>)
0x1830b7d47  nop
0x1830b7d48  add     [rbx+8], r14
0x1830b7d4c  mov     rax, [rbx+8]
0x1830b7d50  sub     rax, r14
0x1830b7d53  mov     rdx, [rsp+98h+Src]
0x1830b7d5b  xor     ecx, ecx
0x1830b7d5d  mov     r8, rax
0x1830b7d60  sub     r8, rdx
0x1830b7d63  add     r8, 7
0x1830b7d67  shr     r8, 3
0x1830b7d6b  cmp     rdx, rax
0x1830b7d6e  cmova   r8, rcx
0x1830b7d72  test    r8, r8
0x1830b7d75  jz      loc_1830B7E07
0x1830b7d7b  mov     rax, [rsp+98h+var_60]
0x1830b7d80  mov     [rdx], rax
0x1830b7d83  lea     rdx, [rdx+8]
0x1830b7d87  inc     rcx
0x1830b7d8a  cmp     rcx, r8
0x1830b7d8d  jnz     short loc_1830B7D80
0x1830b7d8f  jmp     short loc_1830B7E07
0x1830b7d91  mov     rax, [rsp+98h+arg_20]
0x1830b7d99  mov     r15, [rax]
0x1830b7d9c  mov     rdx, rsi
0x1830b7d9f  sub     rdx, r14; Src
0x1830b7da2  mov     r8, r14; Size
0x1830b7da5  mov     rcx, rsi; void *
0x1830b7da8  call    cs:__imp_memmove
0x1830b7dae  lea     rax, [r14+rsi]
0x1830b7db2  mov     [rbx+8], rax
0x1830b7db6  imul    r8, rdi, -8
0x1830b7dba  mov     rdx, [rsp+98h+Src]; Src
0x1830b7dc2  sub     r8, rdx
0x1830b7dc5  add     r8, rsi; Size
0x1830b7dc8  sub     rsi, r8
0x1830b7dcb  mov     rcx, rsi; void *
0x1830b7dce  call    cs:__imp_memmove
0x1830b7dd4  mov     r8, [rsp+98h+Src]
0x1830b7ddc  lea     rax, [r14+r8]
0x1830b7de0  cmp     r8, rax
0x1830b7de3  jz      short loc_1830B7E07
0x1830b7de5  nop     word ptr [rax+rax+00000000h]
0x1830b7df0  mov     [r8], r15
0x1830b7df3  add     r8, 8
0x1830b7df7  mov     rdx, [rsp+98h+Src]
0x1830b7dff  add     rdx, r14
0x1830b7e02  cmp     r8, rdx
0x1830b7e05  jnz     short loc_1830B7DF0
0x1830b7e07  mov     rcx, [rbx]
0x1830b7e0a  lea     rdx, [rcx+r12*8]
0x1830b7e0e  mov     [r13+0], rdx
0x1830b7e12  mov     rax, r13
0x1830b7e15  add     rsp, 60h
0x1830b7e19  pop     r15
0x1830b7e1b  pop     r14
0x1830b7e1d  pop     r13
0x1830b7e1f  pop     r12
0x1830b7e21  pop     rdi
0x1830b7e22  pop     rsi
0x1830b7e23  pop     rbx
0x1830b7e24  retn
```
