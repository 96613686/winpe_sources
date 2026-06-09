# std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> const &)

- ea: `0x1831033d0`
- end: `0x1831036d5`
- name: `?_Insert_n@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@2@@Z`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1830ff610`
- `0x183103290`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x1830f9b50`
- `0x1830f9bb0`
- `0x1831033d0`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x183103689`
- `VCRUNTIME140!memmove` at `0x183103689`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>::_Insert_n(
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
        *((_QWORD *)a1 + 1) = std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
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
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
          a3,
          v11,
          &a3[8 * a4],
          a1,
          v33,
          v38);
        try
        {
          LOBYTE(v34) = v40;
          std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
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
        std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
          v16 + 8 * v18,
          a4,
          a5,
          a1,
          v30);
        v36 = v40;
        LOBYTE(v31) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
          *(_QWORD *)a1,
          a3,
          v17,
          a1,
          v31,
          v36);
        LOBYTE(v37) = v40;
        LOBYTE(v32) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,unsigned int>>>>>>>(
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
0x1831033d0  mov     [rsp+Src], r8
0x1831033d5  push    rbx
0x1831033d6  push    rsi
0x1831033d7  push    rdi
0x1831033d8  push    r12
0x1831033da  push    r13
0x1831033dc  push    r14
0x1831033de  push    r15
0x1831033e0  sub     rsp, 60h
0x1831033e4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1831033ed  mov     rsi, r9
0x1831033f0  mov     rax, r8
0x1831033f3  mov     r13, rdx
0x1831033f6  mov     rdi, rcx
0x1831033f9  mov     [rsp+98h+var_60], rcx
0x1831033fe  mov     r8, [rcx]
0x183103401  mov     r12, rax
0x183103404  sub     r12, r8
0x183103407  sar     r12, 3
0x18310340b  test    r9, r9
0x18310340e  jz      loc_1831036B7
0x183103414  mov     r14, [rcx+8]
0x183103418  mov     rdx, [rcx+10h]
0x18310341c  mov     rcx, rdx
0x18310341f  sub     rcx, r14
0x183103422  sar     rcx, 3
0x183103426  cmp     rcx, r9
0x183103429  jnb     loc_18310355A
0x18310342f  sub     r14, r8
0x183103432  sar     r14, 3
0x183103436  mov     r9, 1FFFFFFFFFFFFFFFh
0x183103440  mov     rax, r9
0x183103443  sub     rax, r14
0x183103446  cmp     rax, rsi
0x183103449  jnb     short loc_183103454
0x18310344b  mov     rcx, rdi
0x18310344e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x183103454  lea     r15, [rsi+r14]
0x183103458  sub     rdx, r8
0x18310345b  sar     rdx, 3
0x18310345f  mov     rax, rdx
0x183103462  shr     rax, 1
0x183103465  sub     r9, rax
0x183103468  add     rax, rdx
0x18310346b  xor     ecx, ecx
0x18310346d  cmp     r9, rdx
0x183103470  cmovnb  rcx, rax
0x183103474  cmp     rcx, r15
0x183103477  cmovnb  r15, rcx
0x18310347b  mov     [rsp+98h+var_58], r15
0x183103480  mov     rdx, r15
0x183103483  mov     rcx, rdi
0x183103486  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x18310348b  mov     rbx, rax
0x18310348e  mov     [rsp+98h+var_50], rax
0x183103493  mov     r14, [rsp+98h+Src]
0x18310349b  sub     r14, [rdi]
0x18310349e  sar     r14, 3
0x1831034a2  lea     rcx, [rax+r14*8]
0x1831034a6  movzx   eax, [rsp+98h+var_68]
0x1831034ab  mov     [rsp+98h+var_78], al
0x1831034af  mov     r9, rdi
0x1831034b2  mov     r8, [rsp+98h+arg_20]
0x1831034ba  mov     rdx, rsi
0x1831034bd  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::integral_constant<bool,0>)
0x1831034c2  movzx   eax, [rsp+98h+var_68]
0x1831034c7  mov     [rsp+98h+var_70], al
0x1831034cb  movzx   eax, [rsp+98h+var_68]
0x1831034d0  mov     [rsp+98h+var_78], al
0x1831034d4  mov     r9, rdi
0x1831034d7  mov     r8, rbx
0x1831034da  mov     rdx, [rsp+98h+Src]
0x1831034e2  mov     rcx, [rdi]
0x1831034e5  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1831034ea  lea     rax, [rsi+r14]
0x1831034ee  lea     r8, [rbx+rax*8]
0x1831034f2  movzx   eax, [rsp+98h+var_68]
0x1831034f7  mov     [rsp+98h+var_70], al
0x1831034fb  movzx   eax, [rsp+98h+var_68]
0x183103500  mov     [rsp+98h+var_78], al
0x183103504  mov     r9, rdi
0x183103507  mov     rdx, [rdi+8]
0x18310350b  mov     rcx, [rsp+98h+Src]
0x183103513  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x183103518  nop
0x183103519  mov     rdx, [rdi]
0x18310351c  mov     rax, [rdi+8]
0x183103520  sub     rax, rdx
0x183103523  sar     rax, 3
0x183103527  add     rsi, rax
0x18310352a  test    rdx, rdx
0x18310352d  jz      short loc_183103542
0x18310352f  mov     r8, [rdi+10h]
0x183103533  sub     r8, rdx
0x183103536  sar     r8, 3
0x18310353a  mov     rcx, rdi
0x18310353d  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x183103542  lea     rax, [rbx+r15*8]
0x183103546  mov     [rdi+10h], rax
0x18310354a  lea     rax, [rbx+rsi*8]
0x18310354e  mov     [rdi+8], rax
0x183103552  mov     [rdi], rbx
0x183103555  jmp     loc_1831036B7
0x18310355a  mov     rcx, r14
0x18310355d  sub     rcx, rax
0x183103560  sar     rcx, 3
0x183103564  cmp     rcx, rsi
0x183103567  jnb     loc_183103634
0x18310356d  mov     rcx, [rsp+98h+arg_20]
0x183103575  mov     rdx, [rcx]
0x183103578  mov     [rsp+98h+var_60], rdx
0x18310357d  lea     rbx, ds:0[r9*8]
0x183103585  lea     r8, [rbx+rax]
0x183103589  movzx   ecx, [rsp+98h+var_68]
0x18310358e  mov     [rsp+98h+var_70], cl
0x183103592  movzx   ecx, [rsp+98h+var_68]
0x183103597  mov     [rsp+98h+var_78], cl
0x18310359b  mov     r9, rdi
0x18310359e  mov     rdx, r14
0x1831035a1  mov     rcx, rax
0x1831035a4  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1831035a9  nop
0x1831035aa  mov     rax, [rdi+8]
0x1831035ae  sub     rax, [rsp+98h+Src]
0x1831035b6  sar     rax, 3
0x1831035ba  sub     rsi, rax
0x1831035bd  movzx   eax, [rsp+98h+var_68]
0x1831035c2  mov     [rsp+98h+var_78], al
0x1831035c6  mov     r9, rdi
0x1831035c9  lea     r8, [rsp+98h+var_60]
0x1831035ce  mov     rdx, rsi
0x1831035d1  mov     rcx, [rdi+8]
0x1831035d5  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::integral_constant<bool,0>)
0x1831035da  nop
0x1831035db  add     [rdi+8], rbx
0x1831035df  mov     rax, [rdi+8]
0x1831035e3  sub     rax, rbx
0x1831035e6  mov     rdx, [rsp+98h+Src]
0x1831035ee  xor     ecx, ecx
0x1831035f0  mov     r8, rax
0x1831035f3  sub     r8, rdx
0x1831035f6  add     r8, 7
0x1831035fa  shr     r8, 3
0x1831035fe  cmp     rdx, rax
0x183103601  cmova   r8, rcx
0x183103605  test    r8, r8
0x183103608  jz      loc_1831036B7
0x18310360e  mov     rax, [rsp+98h+var_60]
0x183103613  nop     dword ptr [rax+00h]
0x183103617  nop     word ptr [rax+rax+00000000h]
0x183103620  mov     [rdx], rax
0x183103623  lea     rdx, [rdx+8]
0x183103627  inc     rcx
0x18310362a  cmp     rcx, r8
0x18310362d  jnz     short loc_183103620
0x18310362f  jmp     loc_1831036B7
0x183103634  mov     rbx, [rsp+98h+arg_20]
0x18310363c  mov     rbx, [rbx]
0x18310363f  lea     r15, ds:0[r9*8]
0x183103647  mov     rcx, r14
0x18310364a  sub     rcx, r15
0x18310364d  movzx   eax, [rsp+98h+var_68]
0x183103652  mov     [rsp+98h+var_70], al
0x183103656  movzx   eax, [rsp+98h+var_68]
0x18310365b  mov     [rsp+98h+var_78], al
0x18310365f  mov     r9, rdi
0x183103662  mov     r8, r14
0x183103665  mov     rdx, r14
0x183103668  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBII@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x18310366d  mov     [rdi+8], rax
0x183103671  imul    r8, rsi, -8
0x183103675  mov     rdx, [rsp+98h+Src]; Src
0x18310367d  sub     r8, rdx
0x183103680  add     r8, r14; Size
0x183103683  sub     r14, r8
0x183103686  mov     rcx, r14; void *
0x183103689  call    cs:__imp_memmove
0x18310368f  mov     r8, [rsp+98h+Src]
0x183103697  lea     rax, [r15+r8]
0x18310369b  cmp     r8, rax
0x18310369e  jz      short loc_1831036B7
0x1831036a0  mov     [r8], rbx
0x1831036a3  add     r8, 8
0x1831036a7  mov     rdx, [rsp+98h+Src]
0x1831036af  add     rdx, r15
0x1831036b2  cmp     r8, rdx
0x1831036b5  jnz     short loc_1831036A0
0x1831036b7  mov     rcx, [rdi]
0x1831036ba  lea     rdx, [rcx+r12*8]
0x1831036be  mov     [r13+0], rdx
0x1831036c2  mov     rax, r13
0x1831036c5  add     rsp, 60h
0x1831036c9  pop     r15
0x1831036cb  pop     r14
0x1831036cd  pop     r13
0x1831036cf  pop     r12
0x1831036d1  pop     rdi
0x1831036d2  pop     rsi
0x1831036d3  pop     rbx
0x1831036d4  retn
```
