# xpsrdr::Cache<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData,xpsrdr::Hash<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,xpsrdr::Weight<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,xpsrdr::D2DImageData>>::insert(std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,xpsrdr::D2DImageData> const &)

- ea: `0x180046920`
- end: `0x180046a3a`
- name: `?insert@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@std@@@std@@@std@@_N@std@@AEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@Z`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180044b78`

## callees

- `0x18000e9b0`
- `0x1800184e8`
- `0x18001ba90`
- `0x18001be30`
- `0x18001ca74`
- `0x18001cb04`
- `0x18001df50`
- `0x18001df68`
- `0x180022a34`
- `0x180035330`
- `0x180046920`
- `0x180046a40`
- `0x180046acc`

## pseudocode

```c
__int64 __fastcall xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 *v10; // rax
  _QWORD v12[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+30h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF

  v13 = xpsrdr::Hash<std::wstring>::operator()(a1, a3);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(
    a1 + 24,
    v12,
    &v13);
  while ( v12[0] != v12[1] )
  {
    v6 = (__int64 *)(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(v12)
                   + 8);
    v7 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6);
    if ( (unsigned __int8)std::operator==<wchar_t>(a3, v7) )
    {
      v8 = std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(v6)
         + 32;
      std::shared_ptr<ID2D1Brush>::operator=(v8, a3 + 32);
      *(_DWORD *)(v8 + 16) = *(_DWORD *)(a3 + 48);
      *(_DWORD *)(v8 + 20) = *(_DWORD *)(a3 + 52);
      v14 = *v6;
      LOBYTE(v13) = 0;
      goto LABEL_7;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(v12);
  }
  xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::resize(a1);
  std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::push_front(a1 + 8, a3);
  v14 = **(_QWORD **)(a1 + 8);
  v9 = std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(
         v12,
         &v13,
         &v14);
  std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(
    a1 + 24,
    &v13,
    v9);
  v10 = *(__int64 **)(a1 + 8);
  LOBYTE(v13) = 1;
  v14 = *v10;
LABEL_7:
  std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(
    a2,
    &v14,
    &v13);
  return a2;
}

```

## disassembly

```asm
0x180046920  mov     [rsp-28h+arg_8], rbx
0x180046925  push    rbp
0x180046926  push    rsi
0x180046927  push    rdi
0x180046928  push    r14
0x18004692a  push    r15
0x18004692c  mov     rbp, rsp
0x18004692f  sub     rsp, 30h
0x180046933  mov     r14, rdx
0x180046936  mov     rdi, r8
0x180046939  mov     rdx, r8
0x18004693c  mov     rbx, rcx
0x18004693f  call    ??R?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@xpsrdr@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; xpsrdr::Hash<std::wstring>::operator()(std::wstring const &)
0x180046944  lea     r8, [rbp+arg_0]
0x180046948  mov     [rbp+arg_0], rax
0x18004694c  lea     rdx, [rbp+var_10]
0x180046950  lea     rcx, [rbx+18h]
0x180046954  call    ?equal_range@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKeyPen@@V?$shared_ptr@U?$GDIResource@PEAUHPEN__@@@xgc@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@V12@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<KeyPen const,std::shared_ptr<xgc::GDIResource<HPEN__ *>>>>>>>>,1>>::equal_range(unsigned __int64 const &)
0x180046959  mov     rax, [rbp+var_8]
0x18004695d  cmp     [rbp+var_10], rax
0x180046961  jz      short loc_1800469C3
0x180046963  lea     rcx, [rbp+var_10]
0x180046967  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>>>>::operator->(void)
0x18004696c  lea     rsi, [rax+8]
0x180046970  mov     rcx, rsi
0x180046973  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x180046978  mov     rdx, rax
0x18004697b  mov     rcx, rdi
0x18004697e  call    ??$?8_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator==<wchar_t>(std::wstring const &,std::wstring const &)
0x180046983  test    al, al
0x180046985  jnz     short loc_180046992
0x180046987  lea     rcx, [rbp+var_10]
0x18004698b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180046990  jmp     short loc_180046959
0x180046992  mov     rcx, rsi
0x180046995  call    ??C?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBKV?$shared_ptr@U?$GDIResource@PEAUHBRUSH__@@@xgc@@@std@@@1@XZ; std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<xgc::GDIResource<HBRUSH__ *>>>>>>::operator->(void)
0x18004699a  lea     rdx, [rdi+20h]
0x18004699e  lea     rbx, [rax+20h]
0x1800469a2  mov     rcx, rbx
0x1800469a5  call    ??4?$shared_ptr@UID2D1Brush@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<ID2D1Brush>::operator=(std::shared_ptr<ID2D1Brush> const &)
0x1800469aa  mov     eax, [rdi+30h]
0x1800469ad  mov     [rbx+10h], eax
0x1800469b0  mov     eax, [rdi+34h]
0x1800469b3  mov     [rbx+14h], eax
0x1800469b6  mov     rax, [rsi]
0x1800469b9  mov     [rbp+arg_10], rax
0x1800469bd  mov     byte ptr [rbp+arg_0], 0
0x1800469c1  jmp     short loc_180046A16
0x1800469c3  movss   xmm1, dword ptr [rbx]
0x1800469c7  mov     rcx, rbx
0x1800469ca  call    ?resize@?$Cache@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@U?$Hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@4@U?$Weight@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@4@@xpsrdr@@QEAAXM@Z; xpsrdr::Cache<std::wstring,xpsrdr::D2DImageData,xpsrdr::Hash<std::wstring>,xpsrdr::Weight<std::wstring,xpsrdr::D2DImageData>>::resize(float)
0x1800469cf  mov     rdx, rdi
0x1800469d2  lea     rcx, [rbx+8]
0x1800469d6  call    ?push_front@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@std@@@2@@std@@QEAAXAEBU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UD2DImageData@xpsrdr@@@2@@Z; std::list<std::pair<std::wstring const,xpsrdr::D2DImageData>>::push_front(std::pair<std::wstring const,xpsrdr::D2DImageData> const &)
0x1800469db  mov     rax, [rbx+8]
0x1800469df  lea     r8, [rbp+arg_10]
0x1800469e3  lea     rcx, [rbp+var_10]
0x1800469e7  mov     rdx, [rax]
0x1800469ea  mov     [rbp+arg_10], rdx
0x1800469ee  lea     rdx, [rbp+arg_0]
0x1800469f2  call    ??$?0AEA_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@$0A@@?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@QEAA@AEA_K$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UColorContext@xpsrdr@@@2@@std@@@std@@@std@@@1@@Z; std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>>>(unsigned __int64 &,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::ColorContext>>>>> &&)
0x1800469f7  mov     r8, rax
0x1800469fa  lea     rdx, [rbp+arg_0]
0x1800469fe  lea     rcx, [rbx+18h]
0x180046a02  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CB_KV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>>>,1>>::insert<1,0>(std::pair<unsigned __int64 const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>> &&)
0x180046a07  mov     rax, [rbx+8]
0x180046a0b  mov     byte ptr [rbp+arg_0], 1
0x180046a0f  mov     rcx, [rax]
0x180046a12  mov     [rbp+arg_10], rcx
0x180046a16  lea     r8, [rbp+arg_0]
0x180046a1a  mov     rcx, r14
0x180046a1d  lea     rdx, [rbp+arg_10]
0x180046a21  call    ??$make_pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@std@@YA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@std@@_N@0@$$QEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@UImage@xpsrdr@@@2@@std@@@std@@@std@@@0@$$QEA_N@Z; std::make_pair<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>>,bool>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<xpsrdr::Image>>>>> &&,bool &&)
0x180046a26  mov     rbx, [rsp+30h+arg_8]
0x180046a2b  mov     rax, r14
0x180046a2e  add     rsp, 30h
0x180046a32  pop     r15
0x180046a34  pop     r14
0x180046a36  pop     rdi
0x180046a37  pop     rsi
0x180046a38  pop     rbp
0x180046a39  retn
```
