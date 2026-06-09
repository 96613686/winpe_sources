# std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> const &)

- ea: `0x1832c8510`
- end: `0x1832c8815`
- name: `?_Insert_n@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@@Z`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1815ad850`
- `0x1832c8390`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x183103b60`
- `0x1832c4390`
- `0x1832c43c0`
- `0x1832c8510`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1832c87c9`
- `VCRUNTIME140!memmove` at `0x1832c87c9`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        CxVector **a5)
{
  __int64 v9; // r8
  __int64 v10; // r12
  __int64 v11; // r14
  __int64 v12; // r14
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r14
  unsigned __int64 v19; // rsi
  __int64 v20; // rbx
  CxVector **v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  CxVector *v24; // rax
  CxVector *v25; // rbx
  __int64 v26; // r15
  CxVector **v27; // r8
  struct CxVector *Pointer; // rax
  char v30; // [rsp+20h] [rbp-78h]
  int v31; // [rsp+20h] [rbp-78h]
  int v32; // [rsp+20h] [rbp-78h]
  char v33; // [rsp+20h] [rbp-78h]
  int v34; // [rsp+20h] [rbp-78h]
  char v35; // [rsp+20h] [rbp-78h]
  char v36; // [rsp+28h] [rbp-70h]
  int v37; // [rsp+28h] [rbp-70h]
  char v38; // [rsp+28h] [rbp-70h]
  char v39; // [rsp+28h] [rbp-70h]
  char v40; // [rsp+30h] [rbp-68h]
  CxVector *v41; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v42; // [rsp+40h] [rbp-58h]
  __int64 v43; // [rsp+48h] [rbp-50h]
  __int64 v44; // [rsp+50h] [rbp-48h]

  v44 = -2;
  v41 = a1;
  v9 = *(_QWORD *)a1;
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
  if ( a4 )
  {
    v11 = *((_QWORD *)a1 + 1);
    if ( (*((_QWORD *)a1 + 2) - v11) >> 3 >= a4 )
    {
      if ( (v11 - (__int64)a3) >> 3 >= a4 )
      {
        v25 = *a5;
        v26 = 8 * a4;
        v39 = v40;
        v35 = v40;
        *((_QWORD *)a1 + 1) = std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
                                v11 - 8 * a4,
                                v11,
                                v11,
                                a1,
                                v35,
                                v39);
        memmove(&a3[8 * a4], a3, v11 + -8LL * a4 - (_QWORD)a3);
        v27 = (CxVector **)a3;
        if ( a3 != &a3[v26] )
        {
          do
            *v27++ = v25;
          while ( v27 != (CxVector **)&a3[v26] );
        }
      }
      else
      {
        v41 = *a5;
        v20 = 8 * a4;
        v38 = v40;
        v33 = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
          a3,
          v11,
          &a3[8 * a4],
          a1,
          v33,
          v38);
        try
        {
          LOBYTE(v34) = v40;
          std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 3),
            &v41,
            a1,
            v34);
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
          v24 = v41;
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
      v14 = (*((_QWORD *)a1 + 2) - v9) >> 3;
      v15 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v42 = v13;
      v16 = std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(
              a1,
              v13);
      v17 = v16;
      v43 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
      try
      {
        v30 = v40;
        std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
          v16 + 8 * v18,
          a4,
          a5,
          a1,
          v30);
        v36 = v40;
        LOBYTE(v31) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
          *(_QWORD *)a1,
          a3,
          v17,
          a1,
          v31,
          v36);
        LOBYTE(v37) = v40;
        LOBYTE(v32) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(
          a3,
          *((_QWORD *)a1 + 1),
          v17 + 8 * (a4 + v18),
          a1,
          v32,
          v37);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v41);
        std::_Wrap_alloc<std::allocator<CxWrapper<CxVarDescriptor>>>::deallocate(Pointer, v43, v42);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<CxWrapper<CxComputation>>::deallocate(
          a1,
          *(_QWORD *)a1,
          (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 3);
      *((_QWORD *)a1 + 2) = v17 + 8 * v13;
      *((_QWORD *)a1 + 1) = v17 + 8 * v19;
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 8 * v10;
  return a2;
}

```

## disassembly

```asm
0x1832c8510  mov     [rsp+Src], r8
0x1832c8515  push    rbx
0x1832c8516  push    rsi
0x1832c8517  push    rdi
0x1832c8518  push    r12
0x1832c851a  push    r13
0x1832c851c  push    r14
0x1832c851e  push    r15
0x1832c8520  sub     rsp, 60h
0x1832c8524  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1832c852d  mov     rsi, r9
0x1832c8530  mov     rax, r8
0x1832c8533  mov     r13, rdx
0x1832c8536  mov     rdi, rcx
0x1832c8539  mov     [rsp+98h+var_60], rcx
0x1832c853e  mov     r8, [rcx]
0x1832c8541  mov     r12, rax
0x1832c8544  sub     r12, r8
0x1832c8547  sar     r12, 3
0x1832c854b  test    r9, r9
0x1832c854e  jz      loc_1832C87F7
0x1832c8554  mov     r14, [rcx+8]
0x1832c8558  mov     rdx, [rcx+10h]
0x1832c855c  mov     rcx, rdx
0x1832c855f  sub     rcx, r14
0x1832c8562  sar     rcx, 3
0x1832c8566  cmp     rcx, r9
0x1832c8569  jnb     loc_1832C869A
0x1832c856f  sub     r14, r8
0x1832c8572  sar     r14, 3
0x1832c8576  mov     r9, 1FFFFFFFFFFFFFFFh
0x1832c8580  mov     rax, r9
0x1832c8583  sub     rax, r14
0x1832c8586  cmp     rax, rsi
0x1832c8589  jnb     short loc_1832C8594
0x1832c858b  mov     rcx, rdi
0x1832c858e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1832c8594  lea     r15, [rsi+r14]
0x1832c8598  sub     rdx, r8
0x1832c859b  sar     rdx, 3
0x1832c859f  mov     rax, rdx
0x1832c85a2  shr     rax, 1
0x1832c85a5  sub     r9, rax
0x1832c85a8  add     rax, rdx
0x1832c85ab  xor     ecx, ecx
0x1832c85ad  cmp     r9, rdx
0x1832c85b0  cmovnb  rcx, rax
0x1832c85b4  cmp     rcx, r15
0x1832c85b7  cmovnb  r15, rcx
0x1832c85bb  mov     [rsp+98h+var_58], r15
0x1832c85c0  mov     rdx, r15
0x1832c85c3  mov     rcx, rdi
0x1832c85c6  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1832c85cb  mov     rbx, rax
0x1832c85ce  mov     [rsp+98h+var_50], rax
0x1832c85d3  mov     r14, [rsp+98h+Src]
0x1832c85db  sub     r14, [rdi]
0x1832c85de  sar     r14, 3
0x1832c85e2  lea     rcx, [rax+r14*8]
0x1832c85e6  movzx   eax, [rsp+98h+var_68]
0x1832c85eb  mov     [rsp+98h+var_78], al
0x1832c85ef  mov     r9, rdi
0x1832c85f2  mov     r8, [rsp+98h+arg_20]
0x1832c85fa  mov     rdx, rsi
0x1832c85fd  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::integral_constant<bool,0>)
0x1832c8602  movzx   eax, [rsp+98h+var_68]
0x1832c8607  mov     [rsp+98h+var_70], al
0x1832c860b  movzx   eax, [rsp+98h+var_68]
0x1832c8610  mov     [rsp+98h+var_78], al
0x1832c8614  mov     r9, rdi
0x1832c8617  mov     r8, rbx
0x1832c861a  mov     rdx, [rsp+98h+Src]
0x1832c8622  mov     rcx, [rdi]
0x1832c8625  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1832c862a  lea     rax, [rsi+r14]
0x1832c862e  lea     r8, [rbx+rax*8]
0x1832c8632  movzx   eax, [rsp+98h+var_68]
0x1832c8637  mov     [rsp+98h+var_70], al
0x1832c863b  movzx   eax, [rsp+98h+var_68]
0x1832c8640  mov     [rsp+98h+var_78], al
0x1832c8644  mov     r9, rdi
0x1832c8647  mov     rdx, [rdi+8]
0x1832c864b  mov     rcx, [rsp+98h+Src]
0x1832c8653  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1832c8658  nop
0x1832c8659  mov     rdx, [rdi]
0x1832c865c  mov     rax, [rdi+8]
0x1832c8660  sub     rax, rdx
0x1832c8663  sar     rax, 3
0x1832c8667  add     rsi, rax
0x1832c866a  test    rdx, rdx
0x1832c866d  jz      short loc_1832C8682
0x1832c866f  mov     r8, [rdi+10h]
0x1832c8673  sub     r8, rdx
0x1832c8676  sar     r8, 3
0x1832c867a  mov     rcx, rdi
0x1832c867d  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1832c8682  lea     rax, [rbx+r15*8]
0x1832c8686  mov     [rdi+10h], rax
0x1832c868a  lea     rax, [rbx+rsi*8]
0x1832c868e  mov     [rdi+8], rax
0x1832c8692  mov     [rdi], rbx
0x1832c8695  jmp     loc_1832C87F7
0x1832c869a  mov     rcx, r14
0x1832c869d  sub     rcx, rax
0x1832c86a0  sar     rcx, 3
0x1832c86a4  cmp     rcx, rsi
0x1832c86a7  jnb     loc_1832C8774
0x1832c86ad  mov     rcx, [rsp+98h+arg_20]
0x1832c86b5  mov     rdx, [rcx]
0x1832c86b8  mov     [rsp+98h+var_60], rdx
0x1832c86bd  lea     rbx, ds:0[r9*8]
0x1832c86c5  lea     r8, [rbx+rax]
0x1832c86c9  movzx   ecx, [rsp+98h+var_68]
0x1832c86ce  mov     [rsp+98h+var_70], cl
0x1832c86d2  movzx   ecx, [rsp+98h+var_68]
0x1832c86d7  mov     [rsp+98h+var_78], cl
0x1832c86db  mov     r9, rdi
0x1832c86de  mov     rdx, r14
0x1832c86e1  mov     rcx, rax
0x1832c86e4  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1832c86e9  nop
0x1832c86ea  mov     rax, [rdi+8]
0x1832c86ee  sub     rax, [rsp+98h+Src]
0x1832c86f6  sar     rax, 3
0x1832c86fa  sub     rsi, rax
0x1832c86fd  movzx   eax, [rsp+98h+var_68]
0x1832c8702  mov     [rsp+98h+var_78], al
0x1832c8706  mov     r9, rdi
0x1832c8709  lea     r8, [rsp+98h+var_60]
0x1832c870e  mov     rdx, rsi
0x1832c8711  mov     rcx, [rdi+8]
0x1832c8715  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::integral_constant<bool,0>)
0x1832c871a  nop
0x1832c871b  add     [rdi+8], rbx
0x1832c871f  mov     rax, [rdi+8]
0x1832c8723  sub     rax, rbx
0x1832c8726  mov     rdx, [rsp+98h+Src]
0x1832c872e  xor     ecx, ecx
0x1832c8730  mov     r8, rax
0x1832c8733  sub     r8, rdx
0x1832c8736  add     r8, 7
0x1832c873a  shr     r8, 3
0x1832c873e  cmp     rdx, rax
0x1832c8741  cmova   r8, rcx
0x1832c8745  test    r8, r8
0x1832c8748  jz      loc_1832C87F7
0x1832c874e  mov     rax, [rsp+98h+var_60]
0x1832c8753  nop     dword ptr [rax+00h]
0x1832c8757  nop     word ptr [rax+rax+00000000h]
0x1832c8760  mov     [rdx], rax
0x1832c8763  lea     rdx, [rdx+8]
0x1832c8767  inc     rcx
0x1832c876a  cmp     rcx, r8
0x1832c876d  jnz     short loc_1832C8760
0x1832c876f  jmp     loc_1832C87F7
0x1832c8774  mov     rbx, [rsp+98h+arg_20]
0x1832c877c  mov     rbx, [rbx]
0x1832c877f  lea     r15, ds:0[r9*8]
0x1832c8787  mov     rcx, r14
0x1832c878a  sub     rcx, r15
0x1832c878d  movzx   eax, [rsp+98h+var_68]
0x1832c8792  mov     [rsp+98h+var_70], al
0x1832c8796  movzx   eax, [rsp+98h+var_68]
0x1832c879b  mov     [rsp+98h+var_78], al
0x1832c879f  mov     r9, rdi
0x1832c87a2  mov     r8, r14
0x1832c87a5  mov     rdx, r14
0x1832c87a8  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1832c87ad  mov     [rdi+8], rax
0x1832c87b1  imul    r8, rsi, -8
0x1832c87b5  mov     rdx, [rsp+98h+Src]; Src
0x1832c87bd  sub     r8, rdx
0x1832c87c0  add     r8, r14; Size
0x1832c87c3  sub     r14, r8
0x1832c87c6  mov     rcx, r14; void *
0x1832c87c9  call    cs:__imp_memmove
0x1832c87cf  mov     r8, [rsp+98h+Src]
0x1832c87d7  lea     rax, [r15+r8]
0x1832c87db  cmp     r8, rax
0x1832c87de  jz      short loc_1832C87F7
0x1832c87e0  mov     [r8], rbx
0x1832c87e3  add     r8, 8
0x1832c87e7  mov     rdx, [rsp+98h+Src]
0x1832c87ef  add     rdx, r15
0x1832c87f2  cmp     r8, rdx
0x1832c87f5  jnz     short loc_1832C87E0
0x1832c87f7  mov     rcx, [rdi]
0x1832c87fa  lea     rdx, [rcx+r12*8]
0x1832c87fe  mov     [r13+0], rdx
0x1832c8802  mov     rax, r13
0x1832c8805  add     rsp, 60h
0x1832c8809  pop     r15
0x1832c880b  pop     r14
0x1832c880d  pop     r13
0x1832c880f  pop     r12
0x1832c8811  pop     rdi
0x1832c8812  pop     rsi
0x1832c8813  pop     rbx
0x1832c8814  retn
```
