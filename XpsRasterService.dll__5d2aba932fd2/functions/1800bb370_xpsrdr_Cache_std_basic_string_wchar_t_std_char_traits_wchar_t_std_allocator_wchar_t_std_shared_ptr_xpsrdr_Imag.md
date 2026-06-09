# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::shared_ptr<xpsrdr::Image>>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::shared_ptr<xpsrdr::Image>> const &)

- ea: `0x1800bb370`
- end: `0x1800bb4e6`
- name: `?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@4@@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800bab9c`

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
- `0x1800bb370`
- `0x1800bb4ec`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bb449`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bb449`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::insert(
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
  xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::resize(a1);
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
0x1800bb370  push    rbp
0x1800bb372  push    rbx
0x1800bb373  push    rsi
0x1800bb374  push    rdi
0x1800bb375  push    r12
0x1800bb377  push    r13
0x1800bb379  push    r14
0x1800bb37b  push    r15
0x1800bb37d  mov     rbp, rsp
0x1800bb380  sub     rsp, 48h
0x1800bb384  mov     r14, r8
0x1800bb387  mov     rsi, rdx
0x1800bb38a  mov     rdi, rcx
0x1800bb38d  mov     rcx, r8
0x1800bb390  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bb395  mov     r9, [r8+10h]
0x1800bb399  lea     rdx, [rax+r9*2]
0x1800bb39d  mov     rcx, rax
0x1800bb3a0  call    ??$CRC32@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@xpsrdr@@YA_KV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@0_K@Z; xpsrdr::CRC32<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,unsigned __int64)
0x1800bb3a5  mov     r12, rax
0x1800bb3a8  mov     [rbp+arg_0], rax
0x1800bb3ac  lea     r13, [rdi+18h]
0x1800bb3b0  lea     r8, [rbp+arg_0]
0x1800bb3b4  lea     rdx, [rbp+var_28]
0x1800bb3b8  mov     rcx, r13
0x1800bb3bb  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800bb3c0  mov     rbx, [rbp+var_28]
0x1800bb3c4  cmp     rbx, [rbp+var_20]
0x1800bb3c8  jz      short loc_1800BB422
0x1800bb3ca  mov     r9, [rbx+28h]
0x1800bb3ce  lea     rcx, [r9+10h]
0x1800bb3d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bb3d7  mov     r8, rax
0x1800bb3da  mov     rcx, r14
0x1800bb3dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bb3e2  mov     rcx, rax
0x1800bb3e5  mov     r9, [r9+20h]
0x1800bb3e9  mov     rdx, [r14+10h]
0x1800bb3ed  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800bb3f2  test    al, al
0x1800bb3f4  jnz     short loc_1800BB401
0x1800bb3f6  lea     rcx, [rbp+var_28]
0x1800bb3fa  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800bb3ff  jmp     short loc_1800BB3C0
0x1800bb401  lea     rdx, [r14+20h]
0x1800bb405  mov     rcx, [rbx+28h]
0x1800bb409  add     rcx, 30h ; '0'
0x1800bb40d  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bb412  mov     rax, [rbx+28h]
0x1800bb416  mov     [rsi], rax
0x1800bb419  mov     byte ptr [rsi+8], 0
0x1800bb41d  jmp     loc_1800BB4D2
0x1800bb422  movss   xmm1, dword ptr [rdi]
0x1800bb426  mov     rcx, rdi
0x1800bb429  call    ?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@5@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<std::wstring,std::shared_ptr<xpsrdr::Image>,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,std::shared_ptr<xpsrdr::Image>>>::resize(float)
0x1800bb42e  lea     r15, [rdi+8]
0x1800bb432  mov     rax, 3FFFFFFFFFFFFFFh
0x1800bb43c  cmp     [r15+8], rax
0x1800bb440  jnz     short loc_1800BB450
0x1800bb442  lea     rcx, aListTooLong; "list too long"
0x1800bb449  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800bb450  mov     rax, [r15]
0x1800bb453  mov     rdi, [rax]
0x1800bb456  mov     [rbp+var_28], r15
0x1800bb45a  mov     [rbp+var_20], 0
0x1800bb462  mov     ecx, 40h ; '@'
0x1800bb467  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800bb46c  mov     rbx, rax
0x1800bb46f  mov     [rbp+var_20], rax
0x1800bb473  lea     rdx, [rax+10h]
0x1800bb477  mov     r8, r14
0x1800bb47a  call    ??$construct@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::construct<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &>(std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>> &,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> * const,std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>> const &)
0x1800bb47f  nop
0x1800bb480  inc     qword ptr [r15+8]
0x1800bb484  mov     rdx, [rdi+8]
0x1800bb488  mov     [rbx], rdi
0x1800bb48b  mov     [rbx+8], rdx
0x1800bb48f  mov     [rbp+var_20], 0
0x1800bb497  mov     [rdi+8], rbx
0x1800bb49b  mov     [rdx], rbx
0x1800bb49e  lea     rcx, [rbp+var_28]
0x1800bb4a2  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>,void *>>>(void)
0x1800bb4a7  mov     [rbp+var_28], r12
0x1800bb4ab  mov     rax, [r15]
0x1800bb4ae  mov     rdx, [rax]
0x1800bb4b1  mov     [rbp+var_20], rdx
0x1800bb4b5  lea     r8, [rbp+var_28]
0x1800bb4b9  lea     rdx, [rbp+var_18]
0x1800bb4bd  mov     rcx, r13
0x1800bb4c0  call    ??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)
0x1800bb4c5  mov     rax, [r15]
0x1800bb4c8  mov     rcx, [rax]
0x1800bb4cb  mov     [rsi], rcx
0x1800bb4ce  mov     byte ptr [rsi+8], 1
0x1800bb4d2  mov     rax, rsi
0x1800bb4d5  add     rsp, 48h
0x1800bb4d9  pop     r15
0x1800bb4db  pop     r14
0x1800bb4dd  pop     r13
0x1800bb4df  pop     r12
0x1800bb4e1  pop     rdi
0x1800bb4e2  pop     rsi
0x1800bb4e3  pop     rbx
0x1800bb4e4  pop     rbp
0x1800bb4e5  retn
```
