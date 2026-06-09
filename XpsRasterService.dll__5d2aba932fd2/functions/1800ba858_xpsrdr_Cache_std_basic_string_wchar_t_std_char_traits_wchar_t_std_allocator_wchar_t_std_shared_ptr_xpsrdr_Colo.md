# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::ColorContext>>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::shared_ptr<xpsrdr::ColorContext>> const &)

- ea: `0x1800ba858`
- end: `0x1800ba9ce`
- name: `?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@4@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800b8c28`

## callees

- `0x1800a7d4c`
- `0x1800aba64`
- `0x1800ad714`
- `0x1800ada28`
- `0x1800adcc0`
- `0x1800add54`
- `0x1800b1bbc`
- `0x1800b3a5c`
- `0x1800b89dc`
- `0x1800b8afc`
- `0x1800ba858`
- `0x1800ba9d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba931`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800ba931`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r12
  _QWORD *v9; // r13
  _QWORD **v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 **v14; // r15
  __int64 v15; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  _QWORD **v20; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-20h]
  char v22[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v23; // [rsp+90h] [rbp+48h] BYREF

  v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v8 = xpsrdr::CRC32<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(
         v6,
         v6 + 2LL * *(_QWORD *)(v7 + 16));
  v23 = v8;
  v9 = (_QWORD *)(a1 + 24);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v20,
    &v23);
  while ( 1 )
  {
    v10 = v20;
    if ( v20 == v21 )
      break;
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20[5] + 2);
    v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v11,
                            *(_QWORD *)(a3 + 16),
                            v13,
                            *(_QWORD *)(v12 + 32)) )
    {
      std::shared_ptr<ID2D1Brush>::operator=(v10[5] + 6, a3 + 32);
      *(_QWORD *)a2 = v10[5];
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(&v20);
  }
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::resize(a1);
  v14 = (__int64 **)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) == 0x3FFFFFFFFFFFFFFLL )
    std::_Xlength_error("list too long");
  v15 = **v14;
  v20 = v14;
  v21 = 0;
  v16 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
  v21 = v16;
  std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::construct<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &>(
    v17,
    v16 + 2,
    a3);
  v14[1] = (__int64 *)((char *)v14[1] + 1);
  v18 = *(_QWORD **)(v15 + 8);
  *v16 = v15;
  v16[1] = v18;
  v21 = 0;
  *(_QWORD *)(v15 + 8) = v16;
  *v18 = v16;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>(&v20);
  v20 = (_QWORD **)v8;
  v21 = (_QWORD *)**v14;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(
    v9,
    (__int64)v22,
    (__int64)&v20);
  *(_QWORD *)a2 = **v14;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800ba858  push    rbp
0x1800ba85a  push    rbx
0x1800ba85b  push    rsi
0x1800ba85c  push    rdi
0x1800ba85d  push    r12
0x1800ba85f  push    r13
0x1800ba861  push    r14
0x1800ba863  push    r15
0x1800ba865  mov     rbp, rsp
0x1800ba868  sub     rsp, 48h
0x1800ba86c  mov     r14, r8
0x1800ba86f  mov     rsi, rdx
0x1800ba872  mov     rdi, rcx
0x1800ba875  mov     rcx, r8
0x1800ba878  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ba87d  mov     r9, [r8+10h]
0x1800ba881  lea     rdx, [rax+r9*2]
0x1800ba885  mov     rcx, rax
0x1800ba888  call    ??$CRC32@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@xpsrdr@@YA_KV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@0_K@Z; xpsrdr::CRC32<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,unsigned __int64)
0x1800ba88d  mov     r12, rax
0x1800ba890  mov     [rbp+arg_0], rax
0x1800ba894  lea     r13, [rdi+18h]
0x1800ba898  lea     r8, [rbp+arg_0]
0x1800ba89c  lea     rdx, [rbp+var_28]
0x1800ba8a0  mov     rcx, r13
0x1800ba8a3  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800ba8a8  mov     rbx, [rbp+var_28]
0x1800ba8ac  cmp     rbx, [rbp+var_20]
0x1800ba8b0  jz      short loc_1800BA90A
0x1800ba8b2  mov     r9, [rbx+28h]
0x1800ba8b6  lea     rcx, [r9+10h]
0x1800ba8ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ba8bf  mov     r8, rax
0x1800ba8c2  mov     rcx, r14
0x1800ba8c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800ba8ca  mov     rcx, rax
0x1800ba8cd  mov     r9, [r9+20h]
0x1800ba8d1  mov     rdx, [r14+10h]
0x1800ba8d5  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800ba8da  test    al, al
0x1800ba8dc  jnz     short loc_1800BA8E9
0x1800ba8de  lea     rcx, [rbp+var_28]
0x1800ba8e2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800ba8e7  jmp     short loc_1800BA8A8
0x1800ba8e9  lea     rdx, [r14+20h]
0x1800ba8ed  mov     rcx, [rbx+28h]
0x1800ba8f1  add     rcx, 30h ; '0'
0x1800ba8f5  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800ba8fa  mov     rax, [rbx+28h]
0x1800ba8fe  mov     [rsi], rax
0x1800ba901  mov     byte ptr [rsi+8], 0
0x1800ba905  jmp     loc_1800BA9BA
0x1800ba90a  movss   xmm1, dword ptr [rdi]
0x1800ba90e  mov     rcx, rdi
0x1800ba911  call    ?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@5@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::ColorContext>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::ColorContext>>>::resize(float)
0x1800ba916  lea     r15, [rdi+8]
0x1800ba91a  mov     rax, 3FFFFFFFFFFFFFFh
0x1800ba924  cmp     [r15+8], rax
0x1800ba928  jnz     short loc_1800BA938
0x1800ba92a  lea     rcx, aListTooLong; "list too long"
0x1800ba931  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800ba938  mov     rax, [r15]
0x1800ba93b  mov     rdi, [rax]
0x1800ba93e  mov     [rbp+var_28], r15
0x1800ba942  mov     [rbp+var_20], 0
0x1800ba94a  mov     ecx, 40h ; '@'
0x1800ba94f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800ba954  mov     rbx, rax
0x1800ba957  mov     [rbp+var_20], rax
0x1800ba95b  lea     rdx, [rax+10h]
0x1800ba95f  mov     r8, r14
0x1800ba962  call    ??$construct@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::construct<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &>(std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>> &,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> * const,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &)
0x1800ba967  nop
0x1800ba968  inc     qword ptr [r15+8]
0x1800ba96c  mov     rdx, [rdi+8]
0x1800ba970  mov     [rbx], rdi
0x1800ba973  mov     [rbx+8], rdx
0x1800ba977  mov     [rbp+var_20], 0
0x1800ba97f  mov     [rdi+8], rbx
0x1800ba983  mov     [rdx], rbx
0x1800ba986  lea     rcx, [rbp+var_28]
0x1800ba98a  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>(void)
0x1800ba98f  mov     [rbp+var_28], r12
0x1800ba993  mov     rax, [r15]
0x1800ba996  mov     rdx, [rax]
0x1800ba999  mov     [rbp+var_20], rdx
0x1800ba99d  lea     r8, [rbp+var_28]
0x1800ba9a1  lea     rdx, [rbp+var_18]
0x1800ba9a5  mov     rcx, r13
0x1800ba9a8  call    ??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)
0x1800ba9ad  mov     rax, [r15]
0x1800ba9b0  mov     rcx, [rax]
0x1800ba9b3  mov     [rsi], rcx
0x1800ba9b6  mov     byte ptr [rsi+8], 1
0x1800ba9ba  mov     rax, rsi
0x1800ba9bd  add     rsp, 48h
0x1800ba9c1  pop     r15
0x1800ba9c3  pop     r14
0x1800ba9c5  pop     r13
0x1800ba9c7  pop     r12
0x1800ba9c9  pop     rdi
0x1800ba9ca  pop     rsi
0x1800ba9cb  pop     rbx
0x1800ba9cc  pop     rbp
0x1800ba9cd  retn
```
