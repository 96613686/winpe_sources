# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Try_emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180011814`
- end: `0x180011982`
- name: `??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `366`
- prototype: `__int64 __fastcall(float *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012e90`

## callees

- `0x1800066d4`
- `0x180010f54`
- `0x180011814`
- `0x180011a10`
- `0x1800124e8`
- `0x180012cd4`
- `0x18001ca28`
- `0x18001cafc`
- `0x18001d234`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001187f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001187f`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Try_emplace<std::wstring const &,>(
        float *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  float v11; // xmm0_4
  __int64 v12; // rcx
  float v13; // xmm1_4
  __int64 v14; // rax
  __int64 v15; // rax
  _QWORD *v17; // [rsp+30h] [rbp-20h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-18h]
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+70h] [rbp+20h] BYREF

  v6 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
    a1,
    &v19,
    a3,
    v6);
  if ( *((_QWORD *)&v19 + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v19 + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0x333333333333333LL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a3;
    v17 = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x50u);
    v18 = v7;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::construct<std::pair<std::wstring const,std::wstring>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(
      v8,
      v7 + 2,
      v9,
      &v20);
    v10 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v10 < 0 )
      v11 = (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1))
          + (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1));
    else
      v11 = (float)(int)v10;
    v12 = *((_QWORD *)a1 + 7);
    if ( v12 < 0 )
    {
      v14 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v12 >> 1);
      v13 = (float)(int)v14 + (float)(int)v14;
    }
    else
    {
      v13 = (float)(int)v12;
    }
    if ( (float)(v11 / v13) > *a1 )
    {
      v15 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        a1,
        v15);
      v19 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                         a1,
                         &v19,
                         (__int64)(v7 + 2),
                         v6);
    }
    v18 = 0;
    *(_QWORD *)a2 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      v19,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(&v17);
  }
  return a2;
}

```

## disassembly

```asm
0x180011814  mov     [rsp-18h+arg_8], rbx
0x180011819  mov     [rsp-18h+arg_10], rsi
0x18001181e  push    rbp
0x18001181f  push    rdi
0x180011820  push    r14
0x180011822  mov     rbp, rsp
0x180011825  sub     rsp, 50h
0x180011829  mov     rsi, r8
0x18001182c  mov     rbx, rdx
0x18001182f  mov     rdi, rcx
0x180011832  mov     rcx, r8
0x180011835  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18001183a  mov     r14, rax
0x18001183d  mov     r9, rax
0x180011840  mov     r8, rsi
0x180011843  lea     rdx, [rbp+var_10]
0x180011847  mov     rcx, rdi
0x18001184a  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18001184f  mov     rcx, qword ptr [rbp+var_10+8]
0x180011853  test    rcx, rcx
0x180011856  jz      short loc_180011864
0x180011858  mov     [rbx], rcx
0x18001185b  mov     byte ptr [rbx+8], 0
0x18001185f  jmp     loc_18001196A
0x180011864  lea     rax, [rdi+8]
0x180011868  mov     rcx, 333333333333333h
0x180011872  cmp     [rax+8], rcx
0x180011876  jnz     short loc_180011886
0x180011878  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18001187f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011886  mov     [rbp+arg_0], rsi
0x18001188a  mov     [rbp+var_20], rax
0x18001188e  mov     [rbp+var_18], 0
0x180011896  mov     ecx, 50h ; 'P'
0x18001189b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800118a0  mov     rsi, rax
0x1800118a3  mov     [rbp+var_18], rax
0x1800118a7  lea     rdx, [rax+10h]
0x1800118ab  lea     r9, [rbp+arg_0]
0x1800118af  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::construct<std::pair<std::wstring const,std::wstring>,std::piecewise_construct_t const &,std::tuple<std::wstring const &>,std::tuple<>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::pair<std::wstring const,std::wstring> * const,std::piecewise_construct_t const &,std::tuple<std::wstring const &> &&,std::tuple<> &&)
0x1800118b4  nop
0x1800118b5  mov     rdx, [rdi+10h]
0x1800118b9  add     rdx, 1
0x1800118bd  xorps   xmm0, xmm0
0x1800118c0  js      short loc_1800118C9
0x1800118c2  cvtsi2ss xmm0, rdx
0x1800118c7  jmp     short loc_1800118E1
0x1800118c9  mov     rcx, rdx
0x1800118cc  shr     rcx, 1
0x1800118cf  mov     rax, rdx
0x1800118d2  and     eax, 1
0x1800118d5  or      rcx, rax
0x1800118d8  cvtsi2ss xmm0, rcx
0x1800118dd  addss   xmm0, xmm0
0x1800118e1  mov     rcx, [rdi+38h]
0x1800118e5  xorps   xmm1, xmm1
0x1800118e8  test    rcx, rcx
0x1800118eb  js      short loc_1800118F4
0x1800118ed  cvtsi2ss xmm1, rcx
0x1800118f2  jmp     short loc_180011909
0x1800118f4  mov     rax, rcx
0x1800118f7  shr     rax, 1
0x1800118fa  and     ecx, 1
0x1800118fd  or      rax, rcx
0x180011900  cvtsi2ss xmm1, rax
0x180011905  addss   xmm1, xmm1
0x180011909  divss   xmm0, xmm1
0x18001190d  comiss  xmm0, dword ptr [rdi]
0x180011910  jbe     short loc_180011940
0x180011912  mov     rcx, rdi
0x180011915  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18001191a  mov     rdx, rax
0x18001191d  mov     rcx, rdi
0x180011920  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x180011925  lea     r8, [rsi+10h]
0x180011929  mov     r9, r14
0x18001192c  lea     rdx, [rbp+var_10]
0x180011930  mov     rcx, rdi
0x180011933  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180011938  movups  xmm0, xmmword ptr [rax]
0x18001193b  movdqu  [rbp+var_10], xmm0
0x180011940  mov     [rbp+var_18], 0
0x180011948  mov     r9, rsi
0x18001194b  mov     r8, qword ptr [rbp+var_10]
0x18001194f  mov     rdx, r14
0x180011952  mov     rcx, rdi
0x180011955  call    ?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> * const)
0x18001195a  mov     [rbx], rax
0x18001195d  mov     byte ptr [rbx+8], 1
0x180011961  lea     rcx, [rbp+var_20]
0x180011965  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(void)
0x18001196a  mov     rax, rbx
0x18001196d  lea     r11, [rsp+50h+var_s0]
0x180011972  mov     rbx, [r11+28h]
0x180011976  mov     rsi, [r11+30h]
0x18001197a  mov     rsp, r11
0x18001197d  pop     r14
0x18001197f  pop     rdi
0x180011980  pop     rbp
0x180011981  retn
```
