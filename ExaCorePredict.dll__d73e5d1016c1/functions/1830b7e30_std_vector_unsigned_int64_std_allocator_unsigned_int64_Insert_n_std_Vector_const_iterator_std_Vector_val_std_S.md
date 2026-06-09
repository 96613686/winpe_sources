# std::vector<unsigned __int64 *,std::allocator<unsigned __int64 *>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned __int64 *>>>,unsigned __int64,unsigned __int64 * const &)

- ea: `0x1830b7e30`
- end: `0x1830b80e5`
- name: `?_Insert_n@?$vector@PEA_KV?$allocator@PEA_K@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEA_K@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEA_K@std@@@std@@@2@_KAEBQEA_K@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1830878f0`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x18306beb0`
- `0x1830b7e30`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1830b7f33`
- `VCRUNTIME140!memmove` at `0x1830b7f50`
- `VCRUNTIME140!memmove` at `0x1830b7fd0`
- `VCRUNTIME140!memmove` at `0x1830b8068`
- `VCRUNTIME140!memmove` at `0x1830b808e`
- `VCRUNTIME140!memmove` at `0x1830b7f33`
- `VCRUNTIME140!memmove` at `0x1830b7f50`
- `VCRUNTIME140!memmove` at `0x1830b7fd0`
- `VCRUNTIME140!memmove` at `0x1830b8068`
- `VCRUNTIME140!memmove` at `0x1830b808e`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned __int64 *>::_Insert_n(
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
          std::_Uninit_alloc_fill_n1<unsigned __int64 * *,unsigned __int64,std::allocator<unsigned __int64 *>>(
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
        std::_Uninit_alloc_fill_n1<unsigned __int64 * *,unsigned __int64,std::allocator<unsigned __int64 *>>(
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
0x1830b7e30  mov     [rsp+Src], r8
0x1830b7e35  push    rbx
0x1830b7e36  push    rsi
0x1830b7e37  push    rdi
0x1830b7e38  push    r12
0x1830b7e3a  push    r13
0x1830b7e3c  push    r14
0x1830b7e3e  push    r15
0x1830b7e40  sub     rsp, 60h
0x1830b7e44  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1830b7e4d  mov     rdi, r9
0x1830b7e50  mov     rax, r8
0x1830b7e53  mov     r13, rdx
0x1830b7e56  mov     rbx, rcx
0x1830b7e59  mov     [rsp+98h+var_60], rcx
0x1830b7e5e  mov     r8, [rcx]
0x1830b7e61  mov     r12, rax
0x1830b7e64  sub     r12, r8
0x1830b7e67  sar     r12, 3
0x1830b7e6b  test    r9, r9
0x1830b7e6e  jz      loc_1830B80C7
0x1830b7e74  mov     rsi, [rcx+8]
0x1830b7e78  mov     rdx, [rcx+10h]
0x1830b7e7c  mov     rcx, rdx
0x1830b7e7f  sub     rcx, rsi
0x1830b7e82  sar     rcx, 3
0x1830b7e86  cmp     rcx, r9
0x1830b7e89  jnb     loc_1830B7F98
0x1830b7e8f  sub     rsi, r8
0x1830b7e92  sar     rsi, 3
0x1830b7e96  mov     r9, 1FFFFFFFFFFFFFFFh
0x1830b7ea0  mov     rax, r9
0x1830b7ea3  sub     rax, rsi
0x1830b7ea6  cmp     rax, rdi
0x1830b7ea9  jnb     short loc_1830B7EB4
0x1830b7eab  mov     rcx, rbx
0x1830b7eae  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1830b7eb4  lea     r15, [rdi+rsi]
0x1830b7eb8  sub     rdx, r8
0x1830b7ebb  sar     rdx, 3
0x1830b7ebf  mov     rax, rdx
0x1830b7ec2  shr     rax, 1
0x1830b7ec5  sub     r9, rax
0x1830b7ec8  add     rax, rdx
0x1830b7ecb  xor     ecx, ecx
0x1830b7ecd  cmp     r9, rdx
0x1830b7ed0  cmovnb  rcx, rax
0x1830b7ed4  cmp     rcx, r15
0x1830b7ed7  cmovnb  r15, rcx
0x1830b7edb  mov     [rsp+98h+var_58], r15
0x1830b7ee0  mov     rdx, r15
0x1830b7ee3  mov     rcx, rbx
0x1830b7ee6  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1830b7eeb  mov     rsi, rax
0x1830b7eee  mov     [rsp+98h+var_50], rax
0x1830b7ef3  mov     r14, [rsp+98h+Src]
0x1830b7efb  sub     r14, [rbx]
0x1830b7efe  sar     r14, 3
0x1830b7f02  lea     rcx, [rax+r14*8]
0x1830b7f06  movzx   eax, [rsp+98h+var_68]
0x1830b7f0b  mov     [rsp+98h+var_78], al
0x1830b7f0f  mov     r9, rbx
0x1830b7f12  mov     r8, [rsp+98h+arg_20]
0x1830b7f1a  mov     rdx, rdi
0x1830b7f1d  call    ??$_Uninit_alloc_fill_n1@PEAPEA_K_KV?$allocator@PEA_K@std@@@std@@YAXPEAPEA_K_KPEBQEA_KAEAU?$_Wrap_alloc@V?$allocator@PEA_K@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<unsigned __int64 * *,unsigned __int64,std::allocator<unsigned __int64 *>>(unsigned __int64 * *,unsigned __int64,unsigned __int64 * const *,std::_Wrap_alloc<std::allocator<unsigned __int64 *>> &,std::integral_constant<bool,0>)
0x1830b7f22  mov     rdx, [rbx]; Src
0x1830b7f25  mov     r8, [rsp+98h+Src]
0x1830b7f2d  sub     r8, rdx; Size
0x1830b7f30  mov     rcx, rsi; void *
0x1830b7f33  call    cs:__imp_memmove
0x1830b7f39  mov     r8, [rbx+8]
0x1830b7f3d  lea     rax, [rdi+r14]
0x1830b7f41  lea     rcx, [rsi+rax*8]; void *
0x1830b7f45  mov     rdx, [rsp+98h+Src]; Src
0x1830b7f4d  sub     r8, rdx; Size
0x1830b7f50  call    cs:__imp_memmove
0x1830b7f56  nop
0x1830b7f57  mov     rdx, [rbx]
0x1830b7f5a  mov     rax, [rbx+8]
0x1830b7f5e  sub     rax, rdx
0x1830b7f61  sar     rax, 3
0x1830b7f65  add     rdi, rax
0x1830b7f68  test    rdx, rdx
0x1830b7f6b  jz      short loc_1830B7F80
0x1830b7f6d  mov     r8, [rbx+10h]
0x1830b7f71  sub     r8, rdx
0x1830b7f74  sar     r8, 3
0x1830b7f78  mov     rcx, rbx
0x1830b7f7b  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1830b7f80  lea     rax, [rsi+r15*8]
0x1830b7f84  mov     [rbx+10h], rax
0x1830b7f88  lea     rax, [rsi+rdi*8]
0x1830b7f8c  mov     [rbx+8], rax
0x1830b7f90  mov     [rbx], rsi
0x1830b7f93  jmp     loc_1830B80C7
0x1830b7f98  mov     rcx, rsi
0x1830b7f9b  sub     rcx, rax
0x1830b7f9e  sar     rcx, 3
0x1830b7fa2  lea     r14, ds:0[r9*8]
0x1830b7faa  cmp     rcx, rdi
0x1830b7fad  jnb     loc_1830B8051
0x1830b7fb3  mov     rcx, [rsp+98h+arg_20]
0x1830b7fbb  mov     rdx, [rcx]
0x1830b7fbe  mov     [rsp+98h+var_60], rdx
0x1830b7fc3  lea     rcx, [r14+rax]; void *
0x1830b7fc7  sub     rsi, rax
0x1830b7fca  mov     r8, rsi; Size
0x1830b7fcd  mov     rdx, rax; Src
0x1830b7fd0  call    cs:__imp_memmove
0x1830b7fd6  nop
0x1830b7fd7  mov     rax, [rbx+8]
0x1830b7fdb  sub     rax, [rsp+98h+Src]
0x1830b7fe3  sar     rax, 3
0x1830b7fe7  sub     rdi, rax
0x1830b7fea  movzx   eax, [rsp+98h+var_68]
0x1830b7fef  mov     [rsp+98h+var_78], al
0x1830b7ff3  mov     r9, rbx
0x1830b7ff6  lea     r8, [rsp+98h+var_60]
0x1830b7ffb  mov     rdx, rdi
0x1830b7ffe  mov     rcx, [rbx+8]
0x1830b8002  call    ??$_Uninit_alloc_fill_n1@PEAPEA_K_KV?$allocator@PEA_K@std@@@std@@YAXPEAPEA_K_KPEBQEA_KAEAU?$_Wrap_alloc@V?$allocator@PEA_K@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<unsigned __int64 * *,unsigned __int64,std::allocator<unsigned __int64 *>>(unsigned __int64 * *,unsigned __int64,unsigned __int64 * const *,std::_Wrap_alloc<std::allocator<unsigned __int64 *>> &,std::integral_constant<bool,0>)
0x1830b8007  nop
0x1830b8008  add     [rbx+8], r14
0x1830b800c  mov     rax, [rbx+8]
0x1830b8010  sub     rax, r14
0x1830b8013  mov     rdx, [rsp+98h+Src]
0x1830b801b  xor     ecx, ecx
0x1830b801d  mov     r8, rax
0x1830b8020  sub     r8, rdx
0x1830b8023  add     r8, 7
0x1830b8027  shr     r8, 3
0x1830b802b  cmp     rdx, rax
0x1830b802e  cmova   r8, rcx
0x1830b8032  test    r8, r8
0x1830b8035  jz      loc_1830B80C7
0x1830b803b  mov     rax, [rsp+98h+var_60]
0x1830b8040  mov     [rdx], rax
0x1830b8043  lea     rdx, [rdx+8]
0x1830b8047  inc     rcx
0x1830b804a  cmp     rcx, r8
0x1830b804d  jnz     short loc_1830B8040
0x1830b804f  jmp     short loc_1830B80C7
0x1830b8051  mov     rax, [rsp+98h+arg_20]
0x1830b8059  mov     r15, [rax]
0x1830b805c  mov     rdx, rsi
0x1830b805f  sub     rdx, r14; Src
0x1830b8062  mov     r8, r14; Size
0x1830b8065  mov     rcx, rsi; void *
0x1830b8068  call    cs:__imp_memmove
0x1830b806e  lea     rax, [r14+rsi]
0x1830b8072  mov     [rbx+8], rax
0x1830b8076  imul    r8, rdi, -8
0x1830b807a  mov     rdx, [rsp+98h+Src]; Src
0x1830b8082  sub     r8, rdx
0x1830b8085  add     r8, rsi; Size
0x1830b8088  sub     rsi, r8
0x1830b808b  mov     rcx, rsi; void *
0x1830b808e  call    cs:__imp_memmove
0x1830b8094  mov     r8, [rsp+98h+Src]
0x1830b809c  lea     rax, [r14+r8]
0x1830b80a0  cmp     r8, rax
0x1830b80a3  jz      short loc_1830B80C7
0x1830b80a5  nop     word ptr [rax+rax+00000000h]
0x1830b80b0  mov     [r8], r15
0x1830b80b3  add     r8, 8
0x1830b80b7  mov     rdx, [rsp+98h+Src]
0x1830b80bf  add     rdx, r14
0x1830b80c2  cmp     r8, rdx
0x1830b80c5  jnz     short loc_1830B80B0
0x1830b80c7  mov     rcx, [rbx]
0x1830b80ca  lea     rdx, [rcx+r12*8]
0x1830b80ce  mov     [r13+0], rdx
0x1830b80d2  mov     rax, r13
0x1830b80d5  add     rsp, 60h
0x1830b80d9  pop     r15
0x1830b80db  pop     r14
0x1830b80dd  pop     r13
0x1830b80df  pop     r12
0x1830b80e1  pop     rdi
0x1830b80e2  pop     rsi
0x1830b80e3  pop     rbx
0x1830b80e4  retn
```
