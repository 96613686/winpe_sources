# std::vector<unsigned __int64,std::allocator<unsigned __int64>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned __int64>>>,unsigned __int64,unsigned __int64 const &)

- ea: `0x1815bb270`
- end: `0x1815bb525`
- name: `?_Insert_n@?$vector@_KV?$allocator@_K@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_K@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_K@std@@@std@@@2@_KAEB_K@Z`
- size: `693`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1815bbcb0`
- `0x183088c70`
- `0x1832826f0`
- `0x183283560`
- `0x1832843c0`
- `0x183285260`
- `0x183286140`
- `0x183287020`
- `0x183288070`
- `0x183288f20`
- `0x183289da0`
- `0x1832a0750`
- `0x1832a0b00`
- `0x1832a0ec0`
- `0x1832a1280`
- `0x1832a1670`
- `0x1832a1a60`
- `0x1832a1ef0`
- `0x1832a22e0`
- `0x1832a26a0`

## callees

- `0x1815adfb0`
- `0x1815bb270`
- `0x1815bbf10`
- `0x183066770`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815bb373`
- `VCRUNTIME140!memmove` at `0x1815bb390`
- `VCRUNTIME140!memmove` at `0x1815bb410`
- `VCRUNTIME140!memmove` at `0x1815bb4a8`
- `VCRUNTIME140!memmove` at `0x1815bb4ce`
- `VCRUNTIME140!memmove` at `0x1815bb373`
- `VCRUNTIME140!memmove` at `0x1815bb390`
- `VCRUNTIME140!memmove` at `0x1815bb410`
- `VCRUNTIME140!memmove` at `0x1815bb4a8`
- `VCRUNTIME140!memmove` at `0x1815bb4ce`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned __int64>::_Insert_n(
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
          std::_Uninit_alloc_fill_n1<unsigned __int64 *,unsigned __int64,std::allocator<unsigned __int64>>(
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
        std::_Uninit_alloc_fill_n1<unsigned __int64 *,unsigned __int64,std::allocator<unsigned __int64>>(
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
0x1815bb270  mov     [rsp+Src], r8
0x1815bb275  push    rbx
0x1815bb276  push    rsi
0x1815bb277  push    rdi
0x1815bb278  push    r12
0x1815bb27a  push    r13
0x1815bb27c  push    r14
0x1815bb27e  push    r15
0x1815bb280  sub     rsp, 60h
0x1815bb284  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1815bb28d  mov     rdi, r9
0x1815bb290  mov     rax, r8
0x1815bb293  mov     r13, rdx
0x1815bb296  mov     rbx, rcx
0x1815bb299  mov     [rsp+98h+var_60], rcx
0x1815bb29e  mov     r8, [rcx]
0x1815bb2a1  mov     r12, rax
0x1815bb2a4  sub     r12, r8
0x1815bb2a7  sar     r12, 3
0x1815bb2ab  test    r9, r9
0x1815bb2ae  jz      loc_1815BB507
0x1815bb2b4  mov     rsi, [rcx+8]
0x1815bb2b8  mov     rdx, [rcx+10h]
0x1815bb2bc  mov     rcx, rdx
0x1815bb2bf  sub     rcx, rsi
0x1815bb2c2  sar     rcx, 3
0x1815bb2c6  cmp     rcx, r9
0x1815bb2c9  jnb     loc_1815BB3D8
0x1815bb2cf  sub     rsi, r8
0x1815bb2d2  sar     rsi, 3
0x1815bb2d6  mov     r9, 1FFFFFFFFFFFFFFFh
0x1815bb2e0  mov     rax, r9
0x1815bb2e3  sub     rax, rsi
0x1815bb2e6  cmp     rax, rdi
0x1815bb2e9  jnb     short loc_1815BB2F4
0x1815bb2eb  mov     rcx, rbx
0x1815bb2ee  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1815bb2f4  lea     r15, [rdi+rsi]
0x1815bb2f8  sub     rdx, r8
0x1815bb2fb  sar     rdx, 3
0x1815bb2ff  mov     rax, rdx
0x1815bb302  shr     rax, 1
0x1815bb305  sub     r9, rax
0x1815bb308  add     rax, rdx
0x1815bb30b  xor     ecx, ecx
0x1815bb30d  cmp     r9, rdx
0x1815bb310  cmovnb  rcx, rax
0x1815bb314  cmp     rcx, r15
0x1815bb317  cmovnb  r15, rcx
0x1815bb31b  mov     [rsp+98h+var_58], r15
0x1815bb320  mov     rdx, r15
0x1815bb323  mov     rcx, rbx
0x1815bb326  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1815bb32b  mov     rsi, rax
0x1815bb32e  mov     [rsp+98h+var_50], rax
0x1815bb333  mov     r14, [rsp+98h+Src]
0x1815bb33b  sub     r14, [rbx]
0x1815bb33e  sar     r14, 3
0x1815bb342  lea     rcx, [rax+r14*8]
0x1815bb346  movzx   eax, [rsp+98h+var_68]
0x1815bb34b  mov     [rsp+98h+var_78], al
0x1815bb34f  mov     r9, rbx
0x1815bb352  mov     r8, [rsp+98h+arg_20]
0x1815bb35a  mov     rdx, rdi
0x1815bb35d  call    ??$_Uninit_alloc_fill_n1@PEA_K_KV?$allocator@_K@std@@@std@@YAXPEA_K_KPEB_KAEAU?$_Wrap_alloc@V?$allocator@_K@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<unsigned __int64 *,unsigned __int64,std::allocator<unsigned __int64>>(unsigned __int64 *,unsigned __int64,unsigned __int64 const *,std::_Wrap_alloc<std::allocator<unsigned __int64>> &,std::integral_constant<bool,0>)
0x1815bb362  mov     rdx, [rbx]; Src
0x1815bb365  mov     r8, [rsp+98h+Src]
0x1815bb36d  sub     r8, rdx; Size
0x1815bb370  mov     rcx, rsi; void *
0x1815bb373  call    cs:__imp_memmove
0x1815bb379  mov     r8, [rbx+8]
0x1815bb37d  lea     rax, [rdi+r14]
0x1815bb381  lea     rcx, [rsi+rax*8]; void *
0x1815bb385  mov     rdx, [rsp+98h+Src]; Src
0x1815bb38d  sub     r8, rdx; Size
0x1815bb390  call    cs:__imp_memmove
0x1815bb396  nop
0x1815bb397  mov     rdx, [rbx]
0x1815bb39a  mov     rax, [rbx+8]
0x1815bb39e  sub     rax, rdx
0x1815bb3a1  sar     rax, 3
0x1815bb3a5  add     rdi, rax
0x1815bb3a8  test    rdx, rdx
0x1815bb3ab  jz      short loc_1815BB3C0
0x1815bb3ad  mov     r8, [rbx+10h]
0x1815bb3b1  sub     r8, rdx
0x1815bb3b4  sar     r8, 3
0x1815bb3b8  mov     rcx, rbx
0x1815bb3bb  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1815bb3c0  lea     rax, [rsi+r15*8]
0x1815bb3c4  mov     [rbx+10h], rax
0x1815bb3c8  lea     rax, [rsi+rdi*8]
0x1815bb3cc  mov     [rbx+8], rax
0x1815bb3d0  mov     [rbx], rsi
0x1815bb3d3  jmp     loc_1815BB507
0x1815bb3d8  mov     rcx, rsi
0x1815bb3db  sub     rcx, rax
0x1815bb3de  sar     rcx, 3
0x1815bb3e2  lea     r14, ds:0[r9*8]
0x1815bb3ea  cmp     rcx, rdi
0x1815bb3ed  jnb     loc_1815BB491
0x1815bb3f3  mov     rcx, [rsp+98h+arg_20]
0x1815bb3fb  mov     rdx, [rcx]
0x1815bb3fe  mov     [rsp+98h+var_60], rdx
0x1815bb403  lea     rcx, [r14+rax]; void *
0x1815bb407  sub     rsi, rax
0x1815bb40a  mov     r8, rsi; Size
0x1815bb40d  mov     rdx, rax; Src
0x1815bb410  call    cs:__imp_memmove
0x1815bb416  nop
0x1815bb417  mov     rax, [rbx+8]
0x1815bb41b  sub     rax, [rsp+98h+Src]
0x1815bb423  sar     rax, 3
0x1815bb427  sub     rdi, rax
0x1815bb42a  movzx   eax, [rsp+98h+var_68]
0x1815bb42f  mov     [rsp+98h+var_78], al
0x1815bb433  mov     r9, rbx
0x1815bb436  lea     r8, [rsp+98h+var_60]
0x1815bb43b  mov     rdx, rdi
0x1815bb43e  mov     rcx, [rbx+8]
0x1815bb442  call    ??$_Uninit_alloc_fill_n1@PEA_K_KV?$allocator@_K@std@@@std@@YAXPEA_K_KPEB_KAEAU?$_Wrap_alloc@V?$allocator@_K@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<unsigned __int64 *,unsigned __int64,std::allocator<unsigned __int64>>(unsigned __int64 *,unsigned __int64,unsigned __int64 const *,std::_Wrap_alloc<std::allocator<unsigned __int64>> &,std::integral_constant<bool,0>)
0x1815bb447  nop
0x1815bb448  add     [rbx+8], r14
0x1815bb44c  mov     rax, [rbx+8]
0x1815bb450  sub     rax, r14
0x1815bb453  mov     rdx, [rsp+98h+Src]
0x1815bb45b  xor     ecx, ecx
0x1815bb45d  mov     r8, rax
0x1815bb460  sub     r8, rdx
0x1815bb463  add     r8, 7
0x1815bb467  shr     r8, 3
0x1815bb46b  cmp     rdx, rax
0x1815bb46e  cmova   r8, rcx
0x1815bb472  test    r8, r8
0x1815bb475  jz      loc_1815BB507
0x1815bb47b  mov     rax, [rsp+98h+var_60]
0x1815bb480  mov     [rdx], rax
0x1815bb483  lea     rdx, [rdx+8]
0x1815bb487  inc     rcx
0x1815bb48a  cmp     rcx, r8
0x1815bb48d  jnz     short loc_1815BB480
0x1815bb48f  jmp     short loc_1815BB507
0x1815bb491  mov     rax, [rsp+98h+arg_20]
0x1815bb499  mov     r15, [rax]
0x1815bb49c  mov     rdx, rsi
0x1815bb49f  sub     rdx, r14; Src
0x1815bb4a2  mov     r8, r14; Size
0x1815bb4a5  mov     rcx, rsi; void *
0x1815bb4a8  call    cs:__imp_memmove
0x1815bb4ae  lea     rax, [r14+rsi]
0x1815bb4b2  mov     [rbx+8], rax
0x1815bb4b6  imul    r8, rdi, -8
0x1815bb4ba  mov     rdx, [rsp+98h+Src]; Src
0x1815bb4c2  sub     r8, rdx
0x1815bb4c5  add     r8, rsi; Size
0x1815bb4c8  sub     rsi, r8
0x1815bb4cb  mov     rcx, rsi; void *
0x1815bb4ce  call    cs:__imp_memmove
0x1815bb4d4  mov     r8, [rsp+98h+Src]
0x1815bb4dc  lea     rax, [r14+r8]
0x1815bb4e0  cmp     r8, rax
0x1815bb4e3  jz      short loc_1815BB507
0x1815bb4e5  nop     word ptr [rax+rax+00000000h]
0x1815bb4f0  mov     [r8], r15
0x1815bb4f3  add     r8, 8
0x1815bb4f7  mov     rdx, [rsp+98h+Src]
0x1815bb4ff  add     rdx, r14
0x1815bb502  cmp     r8, rdx
0x1815bb505  jnz     short loc_1815BB4F0
0x1815bb507  mov     rcx, [rbx]
0x1815bb50a  lea     rdx, [rcx+r12*8]
0x1815bb50e  mov     [r13+0], rdx
0x1815bb512  mov     rax, r13
0x1815bb515  add     rsp, 60h
0x1815bb519  pop     r15
0x1815bb51b  pop     r14
0x1815bb51d  pop     r13
0x1815bb51f  pop     r12
0x1815bb521  pop     rdi
0x1815bb522  pop     rsi
0x1815bb523  pop     rbx
0x1815bb524  retn
```
