# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,xpsrdr::D2DImageData> const &)

- ea: `0x1800bd420`
- end: `0x1800bd5a6`
- name: `?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@Z`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800bb6e4`

## callees

- `0x1800a7d4c`
- `0x1800aba64`
- `0x1800ad714`
- `0x1800ada28`
- `0x1800adcc0`
- `0x1800add54`
- `0x1800b1bbc`
- `0x1800b3a5c`
- `0x1800bb66c`
- `0x1800bb6b4`
- `0x1800bd420`
- `0x1800bd5ac`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bd508`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800bd508`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // r12
  __int64 v9; // r13
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 **v15; // rsi
  __int64 v16; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  _QWORD *v19; // rdx
  __int64 v21; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-20h]
  char v23[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v24; // [rsp+90h] [rbp+48h] BYREF

  v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v8 = xpsrdr::CRC32<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(
         v6,
         v6 + 2LL * *(_QWORD *)(v7 + 16));
  v24 = v8;
  v9 = a1 + 24;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(
    a1 + 24,
    &v21,
    &v24);
  while ( 1 )
  {
    v10 = v21;
    if ( (_QWORD *)v21 == v22 )
      break;
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*(_QWORD *)(v21 + 40) + 16LL);
    v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                            v11,
                            *(_QWORD *)(a3 + 16),
                            v13,
                            *(_QWORD *)(v12 + 32)) )
    {
      v14 = *(_QWORD *)(v10 + 40);
      std::shared_ptr<ID2D1Brush>::operator=(v14 + 48, a3 + 32);
      *(_DWORD *)(v14 + 64) = *(_DWORD *)(a3 + 48);
      *(_DWORD *)(v14 + 68) = *(_DWORD *)(a3 + 52);
      *(_QWORD *)a2 = *(_QWORD *)(v10 + 40);
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(&v21);
  }
  xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::resize(a1);
  v15 = (__int64 **)(a1 + 8);
  if ( *(_QWORD *)(a1 + 16) == 0x38E38E38E38E38ELL )
    std::_Xlength_error("list too long");
  v16 = **v15;
  v21 = a1 + 8;
  v22 = 0;
  v17 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(72);
  v22 = v17;
  std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::construct<std::pair<std::wstring const,xpsrdr::D2DImageData>,std::pair<std::wstring const,xpsrdr::D2DImageData> const &>(
    v18,
    v17 + 2,
    a3);
  v15[1] = (__int64 *)((char *)v15[1] + 1);
  v19 = *(_QWORD **)(v16 + 8);
  *v17 = v16;
  v17[1] = v19;
  v22 = 0;
  *(_QWORD *)(v16 + 8) = v17;
  *v19 = v17;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>(&v21);
  v21 = v8;
  v22 = (_QWORD *)**v15;
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(
    v9,
    v23,
    &v21);
  *(_QWORD *)a2 = **v15;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800bd420  push    rbp
0x1800bd422  push    rbx
0x1800bd423  push    rsi
0x1800bd424  push    rdi
0x1800bd425  push    r12
0x1800bd427  push    r13
0x1800bd429  push    r14
0x1800bd42b  push    r15
0x1800bd42d  mov     rbp, rsp
0x1800bd430  sub     rsp, 48h
0x1800bd434  mov     r15, r8
0x1800bd437  mov     r14, rdx
0x1800bd43a  mov     rbx, rcx
0x1800bd43d  mov     rcx, r8
0x1800bd440  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bd445  mov     r9, [r8+10h]
0x1800bd449  lea     rdx, [rax+r9*2]
0x1800bd44d  mov     rcx, rax
0x1800bd450  call    ??$CRC32@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@xpsrdr@@YA_KV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@0_K@Z; xpsrdr::CRC32<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,unsigned __int64)
0x1800bd455  mov     r12, rax
0x1800bd458  mov     [rbp+arg_0], rax
0x1800bd45c  lea     r13, [rbx+18h]
0x1800bd460  lea     r8, [rbp+arg_0]
0x1800bd464  lea     rdx, [rbp+var_28]
0x1800bd468  mov     rcx, r13
0x1800bd46b  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x1800bd470  mov     rsi, [rbp+var_28]
0x1800bd474  cmp     rsi, [rbp+var_20]
0x1800bd478  jz      short loc_1800BD4E1
0x1800bd47a  mov     r9, [rsi+28h]
0x1800bd47e  lea     rcx, [r9+10h]
0x1800bd482  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bd487  mov     r8, rax
0x1800bd48a  mov     rcx, r15
0x1800bd48d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800bd492  mov     rcx, rax
0x1800bd495  mov     r9, [r9+20h]
0x1800bd499  mov     rdx, [r15+10h]
0x1800bd49d  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800bd4a2  test    al, al
0x1800bd4a4  jnz     short loc_1800BD4B1
0x1800bd4a6  lea     rcx, [rbp+var_28]
0x1800bd4aa  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,xpsrdr::D2DImageData>>>>>>>,std::_Iterator_base0>::operator++(void)
0x1800bd4af  jmp     short loc_1800BD470
0x1800bd4b1  mov     rbx, [rsi+28h]
0x1800bd4b5  lea     rdx, [r15+20h]
0x1800bd4b9  lea     rcx, [rbx+30h]
0x1800bd4bd  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800bd4c2  mov     eax, [r15+30h]
0x1800bd4c6  mov     [rbx+40h], eax
0x1800bd4c9  mov     eax, [r15+34h]
0x1800bd4cd  mov     [rbx+44h], eax
0x1800bd4d0  mov     rax, [rsi+28h]
0x1800bd4d4  mov     [r14], rax
0x1800bd4d7  mov     byte ptr [r14+8], 0
0x1800bd4dc  jmp     loc_1800BD592
0x1800bd4e1  movss   xmm1, dword ptr [rbx]
0x1800bd4e5  mov     rcx, rbx
0x1800bd4e8  call    ?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::resize(float)
0x1800bd4ed  lea     rsi, [rbx+8]
0x1800bd4f1  mov     rax, 38E38E38E38E38Eh
0x1800bd4fb  cmp     [rsi+8], rax
0x1800bd4ff  jnz     short loc_1800BD50F
0x1800bd501  lea     rcx, aListTooLong; "list too long"
0x1800bd508  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800bd50f  mov     rax, [rsi]
0x1800bd512  mov     rdi, [rax]
0x1800bd515  mov     [rbp+var_28], rsi
0x1800bd519  mov     [rbp+var_20], 0
0x1800bd521  mov     ecx, 48h ; 'H'
0x1800bd526  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800bd52b  mov     rbx, rax
0x1800bd52e  mov     [rbp+var_20], rax
0x1800bd532  lea     rdx, [rax+10h]
0x1800bd536  mov     r8, r15
0x1800bd539  call    ??$construct@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@AEBU12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@1@AEBU31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::construct<std::pair<std::wstring const,xpsrdr::D2DImageData>,std::pair<std::wstring const,xpsrdr::D2DImageData> const &>(std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>> &,std::pair<std::wstring const,xpsrdr::D2DImageData> * const,std::pair<std::wstring const,xpsrdr::D2DImageData> const &)
0x1800bd53e  nop
0x1800bd53f  inc     qword ptr [rsi+8]
0x1800bd543  mov     rdx, [rdi+8]
0x1800bd547  mov     [rbx], rdi
0x1800bd54a  mov     [rbx+8], rdx
0x1800bd54e  mov     [rbp+var_20], 0
0x1800bd556  mov     [rdi+8], rbx
0x1800bd55a  mov     [rdx], rbx
0x1800bd55d  lea     rcx, [rbp+var_28]
0x1800bd561  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,xpsrdr::D2DImageData>,void *>>>(void)
0x1800bd566  mov     [rbp+var_28], r12
0x1800bd56a  mov     rax, [rsi]
0x1800bd56d  mov     rdx, [rax]
0x1800bd570  mov     [rbp+var_20], rdx
0x1800bd574  lea     r8, [rbp+var_28]
0x1800bd578  lea     rdx, [rbp+var_18]
0x1800bd57c  mov     rcx, r13
0x1800bd57f  call    ??$_Emplace@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyFontFace@xpsrdr@@V?$shared_ptr@UIDWriteFontFace@@@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>,1>>::_Emplace<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>>>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<xpsrdr::KeyFontFace const,std::shared_ptr<IDWriteFontFace>>>>>> &&)
0x1800bd584  mov     rax, [rsi]
0x1800bd587  mov     rcx, [rax]
0x1800bd58a  mov     [r14], rcx
0x1800bd58d  mov     byte ptr [r14+8], 1
0x1800bd592  mov     rax, r14
0x1800bd595  add     rsp, 48h
0x1800bd599  pop     r15
0x1800bd59b  pop     r14
0x1800bd59d  pop     r13
0x1800bd59f  pop     r12
0x1800bd5a1  pop     rdi
0x1800bd5a2  pop     rsi
0x1800bd5a3  pop     rbx
0x1800bd5a4  pop     rbp
0x1800bd5a5  retn
```
