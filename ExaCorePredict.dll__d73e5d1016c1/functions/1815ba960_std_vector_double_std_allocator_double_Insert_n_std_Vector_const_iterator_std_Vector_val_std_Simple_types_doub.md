# std::vector<double,std::allocator<double>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<double>>>,unsigned __int64,double const &)

- ea: `0x1815ba960`
- end: `0x1815bac23`
- name: `?_Insert_n@?$vector@NV?$allocator@N@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@N@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@N@std@@@std@@@2@_KAEBN@Z`
- size: `707`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x182de78b0`
- `0x1830875c0`
- `0x183281d50`
- `0x183282bf0`
- `0x183283a50`
- `0x1832848b0`
- `0x183285790`
- `0x183286670`
- `0x183287570`
- `0x1832885b0`
- `0x183289410`
- `0x1832a0470`
- `0x1832a0840`
- `0x1832a0bf0`
- `0x1832a0fb0`
- `0x1832a13a0`
- `0x1832a1790`
- `0x1832a1b80`
- `0x1832a2020`
- `0x1832a23d0`

## callees

- `0x1815adef0`
- `0x1815ba960`
- `0x1815bbf10`
- `0x183066770`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815baa68`
- `VCRUNTIME140!memmove` at `0x1815baa85`
- `VCRUNTIME140!memmove` at `0x1815bab07`
- `VCRUNTIME140!memmove` at `0x1815babaa`
- `VCRUNTIME140!memmove` at `0x1815babd0`
- `VCRUNTIME140!memmove` at `0x1815baa68`
- `VCRUNTIME140!memmove` at `0x1815baa85`
- `VCRUNTIME140!memmove` at `0x1815bab07`
- `VCRUNTIME140!memmove` at `0x1815babaa`
- `VCRUNTIME140!memmove` at `0x1815babd0`

## pseudocode

```c
_QWORD *__fastcall std::vector<double>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        CxVector **a5)
{
  _BYTE *v9; // r8
  __int64 v10; // r15
  char *v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // r13
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
  CxVector *v24; // xmm0_8
  CxVector *v25; // xmm6_8
  CxVector **v26; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-88h]
  char v30; // [rsp+20h] [rbp-88h]
  char v31; // [rsp+30h] [rbp-78h]
  CxVector *v32; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-68h]
  __int64 v34; // [rsp+48h] [rbp-60h]
  __int64 v35; // [rsp+50h] [rbp-58h]

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
          std::_Uninit_alloc_fill_n1<double *,unsigned __int64,std::allocator<double>>(
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
        std::_Uninit_alloc_fill_n1<double *,unsigned __int64,std::allocator<double>>(v16 + 8 * v18, a4, a5, a1, v29);
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
0x1815ba960  mov     [rsp+Src], r8
0x1815ba965  push    rbx
0x1815ba966  push    rsi
0x1815ba967  push    rdi
0x1815ba968  push    r12
0x1815ba96a  push    r13
0x1815ba96c  push    r14
0x1815ba96e  push    r15
0x1815ba970  sub     rsp, 70h
0x1815ba974  mov     [rsp+0A8h+var_58], 0FFFFFFFFFFFFFFFEh
0x1815ba97d  movaps  [rsp+0A8h+var_48], xmm6
0x1815ba982  mov     rdi, r9
0x1815ba985  mov     rax, r8
0x1815ba988  mov     r12, rdx
0x1815ba98b  mov     rbx, rcx
0x1815ba98e  mov     [rsp+0A8h+var_70], rcx
0x1815ba993  mov     r8, [rcx]
0x1815ba996  mov     r15, rax
0x1815ba999  sub     r15, r8
0x1815ba99c  sar     r15, 3
0x1815ba9a0  test    r9, r9
0x1815ba9a3  jz      loc_1815BAC00
0x1815ba9a9  mov     rsi, [rcx+8]
0x1815ba9ad  mov     rdx, [rcx+10h]
0x1815ba9b1  mov     rcx, rdx
0x1815ba9b4  sub     rcx, rsi
0x1815ba9b7  sar     rcx, 3
0x1815ba9bb  cmp     rcx, r9
0x1815ba9be  jnb     loc_1815BAACD
0x1815ba9c4  sub     rsi, r8
0x1815ba9c7  sar     rsi, 3
0x1815ba9cb  mov     r9, 1FFFFFFFFFFFFFFFh
0x1815ba9d5  mov     rax, r9
0x1815ba9d8  sub     rax, rsi
0x1815ba9db  cmp     rax, rdi
0x1815ba9de  jnb     short loc_1815BA9E9
0x1815ba9e0  mov     rcx, rbx
0x1815ba9e3  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1815ba9e9  lea     r13, [rdi+rsi]
0x1815ba9ed  sub     rdx, r8
0x1815ba9f0  sar     rdx, 3
0x1815ba9f4  mov     rax, rdx
0x1815ba9f7  shr     rax, 1
0x1815ba9fa  sub     r9, rax
0x1815ba9fd  add     rax, rdx
0x1815baa00  xor     ecx, ecx
0x1815baa02  cmp     r9, rdx
0x1815baa05  cmovnb  rcx, rax
0x1815baa09  cmp     rcx, r13
0x1815baa0c  cmovnb  r13, rcx
0x1815baa10  mov     [rsp+0A8h+var_68], r13
0x1815baa15  mov     rdx, r13
0x1815baa18  mov     rcx, rbx
0x1815baa1b  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1815baa20  mov     rsi, rax
0x1815baa23  mov     [rsp+0A8h+var_60], rax
0x1815baa28  mov     r14, [rsp+0A8h+Src]
0x1815baa30  sub     r14, [rbx]
0x1815baa33  sar     r14, 3
0x1815baa37  lea     rcx, [rax+r14*8]
0x1815baa3b  movzx   eax, [rsp+0A8h+var_78]
0x1815baa40  mov     [rsp+0A8h+var_88], al
0x1815baa44  mov     r9, rbx
0x1815baa47  mov     r8, [rsp+0A8h+arg_20]
0x1815baa4f  mov     rdx, rdi
0x1815baa52  call    ??$_Uninit_alloc_fill_n1@PEAN_KV?$allocator@N@std@@@std@@YAXPEAN_KPEBNAEAU?$_Wrap_alloc@V?$allocator@N@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<double *,unsigned __int64,std::allocator<double>>(double *,unsigned __int64,double const *,std::_Wrap_alloc<std::allocator<double>> &,std::integral_constant<bool,0>)
0x1815baa57  mov     rdx, [rbx]; Src
0x1815baa5a  mov     r8, [rsp+0A8h+Src]
0x1815baa62  sub     r8, rdx; Size
0x1815baa65  mov     rcx, rsi; void *
0x1815baa68  call    cs:__imp_memmove
0x1815baa6e  mov     r8, [rbx+8]
0x1815baa72  lea     rax, [rdi+r14]
0x1815baa76  lea     rcx, [rsi+rax*8]; void *
0x1815baa7a  mov     rdx, [rsp+0A8h+Src]; Src
0x1815baa82  sub     r8, rdx; Size
0x1815baa85  call    cs:__imp_memmove
0x1815baa8b  nop
0x1815baa8c  mov     rdx, [rbx]
0x1815baa8f  mov     rax, [rbx+8]
0x1815baa93  sub     rax, rdx
0x1815baa96  sar     rax, 3
0x1815baa9a  add     rdi, rax
0x1815baa9d  test    rdx, rdx
0x1815baaa0  jz      short loc_1815BAAB5
0x1815baaa2  mov     r8, [rbx+10h]
0x1815baaa6  sub     r8, rdx
0x1815baaa9  sar     r8, 3
0x1815baaad  mov     rcx, rbx
0x1815baab0  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1815baab5  lea     rax, [rsi+r13*8]
0x1815baab9  mov     [rbx+10h], rax
0x1815baabd  lea     rax, [rsi+rdi*8]
0x1815baac1  mov     [rbx+8], rax
0x1815baac5  mov     [rbx], rsi
0x1815baac8  jmp     loc_1815BAC00
0x1815baacd  mov     rcx, rsi
0x1815baad0  sub     rcx, rax
0x1815baad3  sar     rcx, 3
0x1815baad7  lea     r14, ds:0[r9*8]
0x1815baadf  cmp     rcx, rdi
0x1815baae2  jnb     loc_1815BAB92
0x1815baae8  mov     rcx, [rsp+0A8h+arg_20]
0x1815baaf0  movsd   xmm0, qword ptr [rcx]
0x1815baaf4  movsd   [rsp+0A8h+var_70], xmm0
0x1815baafa  lea     rcx, [r14+rax]; void *
0x1815baafe  sub     rsi, rax
0x1815bab01  mov     r8, rsi; Size
0x1815bab04  mov     rdx, rax; Src
0x1815bab07  call    cs:__imp_memmove
0x1815bab0d  nop
0x1815bab0e  mov     rax, [rbx+8]
0x1815bab12  sub     rax, [rsp+0A8h+Src]
0x1815bab1a  sar     rax, 3
0x1815bab1e  sub     rdi, rax
0x1815bab21  movzx   eax, [rsp+0A8h+var_78]
0x1815bab26  mov     [rsp+0A8h+var_88], al
0x1815bab2a  mov     r9, rbx
0x1815bab2d  lea     r8, [rsp+0A8h+var_70]
0x1815bab32  mov     rdx, rdi
0x1815bab35  mov     rcx, [rbx+8]
0x1815bab39  call    ??$_Uninit_alloc_fill_n1@PEAN_KV?$allocator@N@std@@@std@@YAXPEAN_KPEBNAEAU?$_Wrap_alloc@V?$allocator@N@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<double *,unsigned __int64,std::allocator<double>>(double *,unsigned __int64,double const *,std::_Wrap_alloc<std::allocator<double>> &,std::integral_constant<bool,0>)
0x1815bab3e  nop
0x1815bab3f  add     [rbx+8], r14
0x1815bab43  mov     rax, [rbx+8]
0x1815bab47  sub     rax, r14
0x1815bab4a  mov     rdx, [rsp+0A8h+Src]
0x1815bab52  xor     ecx, ecx
0x1815bab54  mov     r8, rax
0x1815bab57  sub     r8, rdx
0x1815bab5a  add     r8, 7
0x1815bab5e  shr     r8, 3
0x1815bab62  cmp     rdx, rax
0x1815bab65  cmova   r8, rcx
0x1815bab69  test    r8, r8
0x1815bab6c  jz      loc_1815BAC00
0x1815bab72  movsd   xmm0, [rsp+0A8h+var_70]
0x1815bab78  nop     dword ptr [rax+rax+00000000h]
0x1815bab80  movsd   qword ptr [rdx], xmm0
0x1815bab84  lea     rdx, [rdx+8]
0x1815bab88  inc     rcx
0x1815bab8b  cmp     rcx, r8
0x1815bab8e  jnz     short loc_1815BAB80
0x1815bab90  jmp     short loc_1815BAC00
0x1815bab92  mov     rax, [rsp+0A8h+arg_20]
0x1815bab9a  movsd   xmm6, qword ptr [rax]
0x1815bab9e  mov     rdx, rsi
0x1815baba1  sub     rdx, r14; Src
0x1815baba4  mov     r8, r14; Size
0x1815baba7  mov     rcx, rsi; void *
0x1815babaa  call    cs:__imp_memmove
0x1815babb0  lea     rax, [r14+rsi]
0x1815babb4  mov     [rbx+8], rax
0x1815babb8  imul    r8, rdi, -8
0x1815babbc  mov     rdx, [rsp+0A8h+Src]; Src
0x1815babc4  sub     r8, rdx
0x1815babc7  add     r8, rsi; Size
0x1815babca  sub     rsi, r8
0x1815babcd  mov     rcx, rsi; void *
0x1815babd0  call    cs:__imp_memmove
0x1815babd6  mov     r8, [rsp+0A8h+Src]
0x1815babde  lea     rax, [r14+r8]
0x1815babe2  cmp     r8, rax
0x1815babe5  jz      short loc_1815BAC00
0x1815babe7  movsd   qword ptr [r8], xmm6
0x1815babec  add     r8, 8
0x1815babf0  mov     rdx, [rsp+0A8h+Src]
0x1815babf8  add     rdx, r14
0x1815babfb  cmp     r8, rdx
0x1815babfe  jnz     short loc_1815BABE7
0x1815bac00  mov     rcx, [rbx]
0x1815bac03  lea     rdx, [rcx+r15*8]
0x1815bac07  mov     [r12], rdx
0x1815bac0b  mov     rax, r12
0x1815bac0e  movaps  xmm6, [rsp+0A8h+var_48]
0x1815bac13  add     rsp, 70h
0x1815bac17  pop     r15
0x1815bac19  pop     r14
0x1815bac1b  pop     r13
0x1815bac1d  pop     r12
0x1815bac1f  pop     rdi
0x1815bac20  pop     rsi
0x1815bac21  pop     rbx
0x1815bac22  retn
```
