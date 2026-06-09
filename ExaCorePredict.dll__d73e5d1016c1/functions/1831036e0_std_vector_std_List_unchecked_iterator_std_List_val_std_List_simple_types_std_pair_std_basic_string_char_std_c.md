# std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>>>>>,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>> const &)

- ea: `0x1831036e0`
- end: `0x1831039e5`
- name: `?_Insert_n@?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@2@_KAEBV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@2@@Z`
- size: `773`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1830fae10`
- `0x183103330`

## callees

- `0x1815bbf10`
- `0x183066770`
- `0x1830f9b80`
- `0x1830f9c00`
- `0x1831036e0`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x183103999`
- `VCRUNTIME140!memmove` at `0x183103999`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>::_Insert_n(
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
        *((_QWORD *)a1 + 1) = std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
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
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
          a3,
          v11,
          &a3[8 * a4],
          a1,
          v33,
          v38);
        try
        {
          LOBYTE(v34) = v40;
          std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
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
        std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
          v16 + 8 * v18,
          a4,
          a5,
          a1,
          v30);
        v36 = v40;
        LOBYTE(v31) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
          *(_QWORD *)a1,
          a3,
          v17,
          a1,
          v31,
          v36);
        LOBYTE(v37) = v40;
        LOBYTE(v32) = v40;
        std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,unsigned int>>>>>>>(
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
0x1831036e0  mov     [rsp+Src], r8
0x1831036e5  push    rbx
0x1831036e6  push    rsi
0x1831036e7  push    rdi
0x1831036e8  push    r12
0x1831036ea  push    r13
0x1831036ec  push    r14
0x1831036ee  push    r15
0x1831036f0  sub     rsp, 60h
0x1831036f4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1831036fd  mov     rsi, r9
0x183103700  mov     rax, r8
0x183103703  mov     r13, rdx
0x183103706  mov     rdi, rcx
0x183103709  mov     [rsp+98h+var_60], rcx
0x18310370e  mov     r8, [rcx]
0x183103711  mov     r12, rax
0x183103714  sub     r12, r8
0x183103717  sar     r12, 3
0x18310371b  test    r9, r9
0x18310371e  jz      loc_1831039C7
0x183103724  mov     r14, [rcx+8]
0x183103728  mov     rdx, [rcx+10h]
0x18310372c  mov     rcx, rdx
0x18310372f  sub     rcx, r14
0x183103732  sar     rcx, 3
0x183103736  cmp     rcx, r9
0x183103739  jnb     loc_18310386A
0x18310373f  sub     r14, r8
0x183103742  sar     r14, 3
0x183103746  mov     r9, 1FFFFFFFFFFFFFFFh
0x183103750  mov     rax, r9
0x183103753  sub     rax, r14
0x183103756  cmp     rax, rsi
0x183103759  jnb     short loc_183103764
0x18310375b  mov     rcx, rdi
0x18310375e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x183103764  lea     r15, [rsi+r14]
0x183103768  sub     rdx, r8
0x18310376b  sar     rdx, 3
0x18310376f  mov     rax, rdx
0x183103772  shr     rax, 1
0x183103775  sub     r9, rax
0x183103778  add     rax, rdx
0x18310377b  xor     ecx, ecx
0x18310377d  cmp     r9, rdx
0x183103780  cmovnb  rcx, rax
0x183103784  cmp     rcx, r15
0x183103787  cmovnb  r15, rcx
0x18310378b  mov     [rsp+98h+var_58], r15
0x183103790  mov     rdx, r15
0x183103793  mov     rcx, rdi
0x183103796  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x18310379b  mov     rbx, rax
0x18310379e  mov     [rsp+98h+var_50], rax
0x1831037a3  mov     r14, [rsp+98h+Src]
0x1831037ab  sub     r14, [rdi]
0x1831037ae  sar     r14, 3
0x1831037b2  lea     rcx, [rax+r14*8]
0x1831037b6  movzx   eax, [rsp+98h+var_68]
0x1831037bb  mov     [rsp+98h+var_78], al
0x1831037bf  mov     r9, rdi
0x1831037c2  mov     r8, [rsp+98h+arg_20]
0x1831037ca  mov     rdx, rsi
0x1831037cd  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::integral_constant<bool,0>)
0x1831037d2  movzx   eax, [rsp+98h+var_68]
0x1831037d7  mov     [rsp+98h+var_70], al
0x1831037db  movzx   eax, [rsp+98h+var_68]
0x1831037e0  mov     [rsp+98h+var_78], al
0x1831037e4  mov     r9, rdi
0x1831037e7  mov     r8, rbx
0x1831037ea  mov     rdx, [rsp+98h+Src]
0x1831037f2  mov     rcx, [rdi]
0x1831037f5  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1831037fa  lea     rax, [rsi+r14]
0x1831037fe  lea     r8, [rbx+rax*8]
0x183103802  movzx   eax, [rsp+98h+var_68]
0x183103807  mov     [rsp+98h+var_70], al
0x18310380b  movzx   eax, [rsp+98h+var_68]
0x183103810  mov     [rsp+98h+var_78], al
0x183103814  mov     r9, rdi
0x183103817  mov     rdx, [rdi+8]
0x18310381b  mov     rcx, [rsp+98h+Src]
0x183103823  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x183103828  nop
0x183103829  mov     rdx, [rdi]
0x18310382c  mov     rax, [rdi+8]
0x183103830  sub     rax, rdx
0x183103833  sar     rax, 3
0x183103837  add     rsi, rax
0x18310383a  test    rdx, rdx
0x18310383d  jz      short loc_183103852
0x18310383f  mov     r8, [rdi+10h]
0x183103843  sub     r8, rdx
0x183103846  sar     r8, 3
0x18310384a  mov     rcx, rdi
0x18310384d  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x183103852  lea     rax, [rbx+r15*8]
0x183103856  mov     [rdi+10h], rax
0x18310385a  lea     rax, [rbx+rsi*8]
0x18310385e  mov     [rdi+8], rax
0x183103862  mov     [rdi], rbx
0x183103865  jmp     loc_1831039C7
0x18310386a  mov     rcx, r14
0x18310386d  sub     rcx, rax
0x183103870  sar     rcx, 3
0x183103874  cmp     rcx, rsi
0x183103877  jnb     loc_183103944
0x18310387d  mov     rcx, [rsp+98h+arg_20]
0x183103885  mov     rdx, [rcx]
0x183103888  mov     [rsp+98h+var_60], rdx
0x18310388d  lea     rbx, ds:0[r9*8]
0x183103895  lea     r8, [rbx+rax]
0x183103899  movzx   ecx, [rsp+98h+var_68]
0x18310389e  mov     [rsp+98h+var_70], cl
0x1831038a2  movzx   ecx, [rsp+98h+var_68]
0x1831038a7  mov     [rsp+98h+var_78], cl
0x1831038ab  mov     r9, rdi
0x1831038ae  mov     rdx, r14
0x1831038b1  mov     rcx, rax
0x1831038b4  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x1831038b9  nop
0x1831038ba  mov     rax, [rdi+8]
0x1831038be  sub     rax, [rsp+98h+Src]
0x1831038c6  sar     rax, 3
0x1831038ca  sub     rsi, rax
0x1831038cd  movzx   eax, [rsp+98h+var_68]
0x1831038d2  mov     [rsp+98h+var_78], al
0x1831038d6  mov     r9, rdi
0x1831038d9  lea     r8, [rsp+98h+var_60]
0x1831038de  mov     rdx, rsi
0x1831038e1  mov     rcx, [rdi+8]
0x1831038e5  call    ??$_Uninit_alloc_fill_n1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@_KU?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAXPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@_KPEBV10@AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,unsigned __int64,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> const *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::integral_constant<bool,0>)
0x1831038ea  nop
0x1831038eb  add     [rdi+8], rbx
0x1831038ef  mov     rax, [rdi+8]
0x1831038f3  sub     rax, rbx
0x1831038f6  mov     rdx, [rsp+98h+Src]
0x1831038fe  xor     ecx, ecx
0x183103900  mov     r8, rax
0x183103903  sub     r8, rdx
0x183103906  add     r8, 7
0x18310390a  shr     r8, 3
0x18310390e  cmp     rdx, rax
0x183103911  cmova   r8, rcx
0x183103915  test    r8, r8
0x183103918  jz      loc_1831039C7
0x18310391e  mov     rax, [rsp+98h+var_60]
0x183103923  nop     dword ptr [rax+00h]
0x183103927  nop     word ptr [rax+rax+00000000h]
0x183103930  mov     [rdx], rax
0x183103933  lea     rdx, [rdx+8]
0x183103937  inc     rcx
0x18310393a  cmp     rcx, r8
0x18310393d  jnz     short loc_183103930
0x18310393f  jmp     loc_1831039C7
0x183103944  mov     rbx, [rsp+98h+arg_20]
0x18310394c  mov     rbx, [rbx]
0x18310394f  lea     r15, ds:0[r9*8]
0x183103957  mov     rcx, r14
0x18310395a  sub     rcx, r15
0x18310395d  movzx   eax, [rsp+98h+var_68]
0x183103962  mov     [rsp+98h+var_70], al
0x183103966  movzx   eax, [rsp+98h+var_68]
0x18310396b  mov     [rsp+98h+var_78], al
0x18310396f  mov     r9, rdi
0x183103972  mov     r8, r14
0x183103975  mov     rdx, r14
0x183103978  call    ??$_Uninitialized_move_al_unchecked1@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@2@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@std@@@std@@@std@@@std@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,uint>>>>>>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x18310397d  mov     [rdi+8], rax
0x183103981  imul    r8, rsi, -8
0x183103985  mov     rdx, [rsp+98h+Src]; Src
0x18310398d  sub     r8, rdx
0x183103990  add     r8, r14; Size
0x183103993  sub     r14, r8
0x183103996  mov     rcx, r14; void *
0x183103999  call    cs:__imp_memmove
0x18310399f  mov     r8, [rsp+98h+Src]
0x1831039a7  lea     rax, [r15+r8]
0x1831039ab  cmp     r8, rax
0x1831039ae  jz      short loc_1831039C7
0x1831039b0  mov     [r8], rbx
0x1831039b3  add     r8, 8
0x1831039b7  mov     rdx, [rsp+98h+Src]
0x1831039bf  add     rdx, r15
0x1831039c2  cmp     r8, rdx
0x1831039c5  jnz     short loc_1831039B0
0x1831039c7  mov     rcx, [rdi]
0x1831039ca  lea     rdx, [rcx+r12*8]
0x1831039ce  mov     [r13+0], rdx
0x1831039d2  mov     rax, r13
0x1831039d5  add     rsp, 60h
0x1831039d9  pop     r15
0x1831039db  pop     r14
0x1831039dd  pop     r13
0x1831039df  pop     r12
0x1831039e1  pop     rdi
0x1831039e2  pop     rsi
0x1831039e3  pop     rbx
0x1831039e4  retn
```
